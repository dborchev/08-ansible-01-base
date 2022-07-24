# Самоконтроль выполненения задания

1. Где расположен файл с `some_fact` из второго пункта задания?
  * https://github.com/dborchev/08-ansible-01-base/blob/main/group_vars/all/examp.yml
2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?
  * `ansible-playbook site.yml -i inventory/test.yml`
3. Какой командой можно зашифровать файл?
  * например `ansible-vault encrypt group_vars/deb/examp.yml`
4. Какой командой можно расшифровать файл?
  * например `ansible-vault decrypt group_vars/deb/examp.yml`
5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?
  * например `ansible-vault view group_vars/deb/examp.yml`
  * .
  ```bash
  $ ansible-vault view group_vars/deb/examp.yml
  Vault password:
  ---
    some_fact: "deb default fact"
  ```
6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?
  * в зависимости от места хранения пароля, может потребоваться добавить опции `--vault-password-file` или `--ask-vault-password`
  * например `$ ansible-playbook site.yml -i inventory/prod.yml --ask-vault-pass`
7. Как называется модуль подключения к host на windows?
  * `winrm`: https://docs.ansible.com/ansible/latest/user_guide/windows_winrm.html
  * вполне можно использовать `ssh`: https://docs.ansible.com/ansible/latest/user_guide/windows_setup.html#configuring-ansible-for-ssh-on-windows
    * требует некоторых хотфиксов и версий, описанных там же в документации
  * еще например win.psexec https://docs.ansible.com/ansible/2.4/win_psexec_module.html
8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh
  * `ansible-doc -t connection ssh`
9. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?
  * `remote_user`
