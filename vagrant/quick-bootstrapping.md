**Быстрая разработка bootstrap скриптов**

1. Создаём виртуальную машину
  ```sh
  vagrant init ubuntu/trusty64
  ```

2. Меняем Vagrantfile чтобы в нём была следующая секция

  ```ruby
  config.vm.provision "shell", inline: <<-SHELL
      echo ". /vagrant/bootstrap.sh" >> ~vagrant/.bashrc
      echo ". /vagrant/bootstrap.sh" >> /root/.bashrc
      # Когда тестирование bootstrap.sh будет закончено,
      # раскомить следующие 2 строки:
      # . /vagrant/bootstrap.sh
      # install-all
  SHELL
  ```

3. Создаём *bootstrap.sh* скрипт со следующим содержанием
  ```sh
  #!/bin/bash
  echo "----------------"
  echo 'Bootstrap script loaded from "'$BASH_SOURCE'!"'
  echo "----------------"

  install-all(){
      echo "Installing..."
  }

  reload-bootstrap(){
      . $BASH_SOURCE
  }
  ```

4. Зайдя на сервер, в bash окружении будет самая актуальная версия
*bootstrap.sh*. Можно вызвать `reload-bootstrap` и она обновится.
Все команды из *bootstrap.sh* (`install-all`, `reload-bootstrap`, etc...)
доступны в командной строке.

5. Как всё будет закончено - меняем Vagrantfile следующим образом:
  ```ruby
  config.vm.provision "shell", inline: <<-SHELL
      echo ". /vagrant/bootstrap.sh" >> ~vagrant/.bashrc
      echo ". /vagrant/bootstrap.sh" >> /root/.bashrc
      # Когда тестирование bootstrap.sh будет закончено,
      # раскомить следующие 2 строки:
      . /vagrant/bootstrap.sh
      install-all
  SHELL
  ```
