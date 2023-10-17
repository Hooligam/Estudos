# Gerenciamente de Usuarios e grupos.

---
Em qualquer sistema operacional é muito importante saber gerenciar usuarios e grupos de usuarios.
---

### Gerenciamento de Usuarios:


```
su
```
Trocar de usuário ou obter privilégios de um usuario.

```
useradd
```
Adicionar um novo usuário ao sistema.

```
userdel
```
Excluir um usuário.

```
passwd
```
Alterar ou defini a senha de um usuário.

### Gerenciamento de Grupos:

```
groupadd
```
Adicionar um novo grupo ao sistema.

```
groupdel
```
Excluir um grupo.

```
usermod -aG nome_do_grupo nome_do_usuário
```
Adicionar um usuário a um grupo.

```
gpasswd
```
Configurar a senha de um grupo (para grupos protegidos por senha).

```
gpasswd -d
```
Remove o usuario do grupo.

```
gpasswd -r 
```
Apaga a senha do grupo.

```
gpasswd -A
```
O usuario passa a ser ADM do grupo.

⌨️ com ❤️ por [Elias Assunção](https://github.com/Hooligam) 🔥