---

link: http://askubuntu.com/questions/6176/how-do-i-upgrade-from-x86-to-x64-without-losing-settings

---
Чтобы поставить все программы как на другой системе

1. Сохраняем список установленных пакетов
  ```sh
  $ dpkg --get-selections > ~/installed-software
  ```

2. На другой системе загружаем этот список и даём задачу установить всё
  ```sh
  # dpkg --set-selections < ~/installed-software
  # apt-get -f install
  ```


