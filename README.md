# awesome-ansible

使用 Ansible role ，一键部署 linux/ubuntu 系统常见服务及常见应用

## 实现的 role 如下

| role              | example command                                         | Comment                                                                                                                |
| ----------------- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| docker roles      | ansible-playbook -i environment/ setup_docker.yml       | 安装 docker 和 docker-compose                                                                                          |
| filebrowser roles | ansible-playbook -i environment/ deploy_filebrowser.yml | 部署 filebrowser， FileBrowser 是一个基于 Web 的文件管理器，它允许用户通过网络浏览、创建、编辑、上传、下载和删除文件。 |
| java roles        | ansible-playbook -i environment/ setup_java.yml         | 安装 java 环境。                                                                                                       |
| jenkins roles     | ansible-playbook -i environment/ setup_jenkins.yml      | 部署 jenkins。                                                                                                         |
