# Ansible

[Retour au sommaire](docs/index)

## ansible CLI
- Pinger le GROUP de serveurs:
```bash
 ansible [[GROUP]] -i [[INVENTORY]] -m ping --vault-password=[[FILE_PASSWORD]]
```
- Lancer une COMMANDE bash sur le GROUP de serveurs:
```bash
ansible [[GROUP]] -i [[INVENTORY]] -m ansible.builtin.shell -a "[[COMMANDE]]" --vault-password=[[FILE_PASSWORD]]
```
- Lancer un SCRIPT sur le GROUP de serveurs:
```bash
ansible [[GROUP]] -i [[INVENTORY]] -m ansible.builtin.script -a "[[SCRIPT]] [[ARGUMENTS]]..." --vault-password=[[FILE_PASSWORD]]
```
- Lancer un PLAYBOOK avec seulement les tâches tagger TAG:
```bash
ansible-playbook [[PLAYBOOK]] -i [[INVENTORY]] --vault-password=[[FILE_PASSWORD]] --tags TAG --extra-vars "[[KEY]]=[[VALUE]]..."
```

## ansible vault
- Encrypter un FICHIER:
```bash
ansible-vault encrypt [[FICHIER]]
```
- Encrypter une VARIABLE:
```bash
ansible-vault encrypt_string --vault-password-file [[VAULT_FILE]] [[VARIABLE_VALUE]] --name [[VARIABLE]]
```
- Modifier le FICHIER:
```bash
ansible-vault edit [[FICHIER]]
```
- Decrypter le FICHIER:
```bash
ansible-vault decrypt [[FICHIER]]
```

## Autre
- Initialiser un ROLE:
```bash
ansible-galaxy init [[ROLE]]
```
- Lister l'inventaire:
```bash
ansible-inventory -i [[INVENTORY]] --graph --ask-vault-pass
```
