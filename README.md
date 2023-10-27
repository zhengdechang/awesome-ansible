# awesome-ansible

使用 Ansible role ，一键部署 linux/ubuntu 系统常见服务及常见应用

## 使用
- 执行部署/安装前，请修改environment/hosts中的主机IP和账号密码，保证能够连接上主机，比如
  ```
  [jenkins_server]
  127.0.0.1
  [jenkins_server:vars]
  ansible_ssh_user=devin
  ansible_ssh_pass=devin  
  ansible_become_pass=devin
  ```
  
  注意：若主机中的账号密码都相同，则只需修改[all:vars]中的变量

- 在下列表格中找到需要安装或者部署的软件，执行example command列中的命令，比如：
  
  ```
  ansible-playbook -i environment/ setup_docker.yml 
  ```

## 实现的 role 如下

| role        | example command                                         | Comment                                                                           |
|-------------|---------------------------------------------------------|-----------------------------------------------------------------------------------|
| Docker      | ansible-playbook -i environment/ setup_docker.yml       | 安装 docker 和 docker-compose                                                        |
| Filebrowser | ansible-playbook -i environment/ deploy_filebrowser.yml | 部署 filebrowser， FileBrowser 是一个基于 Web 的文件管理器，它允许用户通过网络浏览、创建、编辑、上传、下载和删除文件。        |
| Java        | ansible-playbook -i environment/ setup_java.yml         | 安装 java 环境。                                                                       |
| Jenkins     | ansible-playbook -i environment/ setup_jenkins.yml      | 部署 jenkins。 Jenkins是一个开源的、基于Java开发的持续集成工具，用于自动化各种任务，包括构建、测试和部署软件项目，从而实现持续集成和持续交付。 |
| GoLand      | ansible-playbook -i environment/ setup_go.yml           | 安装 GoLand  。                                                                      |
