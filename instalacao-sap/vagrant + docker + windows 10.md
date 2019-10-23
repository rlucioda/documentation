A ideia é ter um Linux virtualizado no windows, que dê para rodar o docker e usar o vagrant como um sistema sobre o Windows.
Para não precisar de fazer dual boot, já que tudo o que eu preciso é um terminal Linux que eu posso instalar qualquer coisa com `apt-get`  :)

1) Instalar no windos o cmder, um emulador de console
http://cmder.net/

2) Instalar virtual box
https://www.virtualbox.org/wiki/Downloads

3) Instalar o vagrant
https://www.virtualbox.org/wiki/Downloads

4) Criar um diretorio no Windows para sincronizar com o Vagrant, no meu caso, abrir o cmder os seguintes comandos:
```
bash
mkdir dev
cd dev
mkdir vagrant
cd vagrant
```

5) Criar o arquivo `Vagrantfile` no diretorio vagrant, com o seguinte conteúdo
```
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.synced_folder ".", "/vagrant"
end
``` 
Obs: depois é possível liberar mais portas caso você queria instalar o `mysql` no vagrant e acessar via Workbrenck no Windows.

Obs 2: rodar `vagrant up` como administrator no cmder:
- no cmder apertar `Ctrl + t`
- em "create new console" selecionar "{bash::bash As Admin}"
- marcar a caixinha de "Run as administrator" (ou `alt + r`)
- Clicar em "Start" (ou `alt + S`)

6) Depois de criar `Vagrantfile` é só rodar `vagrant up` e esperar baixar as coisas

7) Depois de instalar tudo, rodar `vagrant ssh`, pronto! Você está no Ubuntu, agora é instalar tudo o que você precisa ou queira :)

8) Agora vamos instalar o `docker` (mais informações detalhadas em https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)
```
sudo apt-get update
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
echo "deb https://apt.dockerproject.org/repo ubuntu-xenial main" | sudo tee /etc/apt/sources.list.d/docker.list
sudo apt-get update
apt-cache policy docker-engine
```
Se mostrar a seguinte mensagem ou algo parecido é sucesso!
```
docker-engine:
  Installed: (none)
  Candidate: 1.11.1-0~xenial
  Version table:
     1.11.1-0~xenial 500
        500 https://apt.dockerproject.org/repo ubuntu-xenial/main amd64 Packages
     1.11.0-0~xenial 500
        500 https://apt.dockerproject.org/repo ubuntu-xenial/main amd64 Packages
```  
Depois é só dar um `sudo apt-get install -y docker-engine` pra instalar de fato o docker!

Pra iniciar o docker quando você dar um `vagrant up` é só rodar `sudo systemctl status docker`

9) Pronto! Recomendo instalar também no vagrant node, npm, bower, gulp, etc
O node é o mais chatinho, se preferir dar uma olhadinha em https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-16-04

10) Os dados sincronizados com Windows no vagrant estão em `/vagrant` ou seja, no vagrant é só entrar no `cd /vagrant`. Neste diretorio estão os arquivos sincronizados de onde você deu `vagrant up`
