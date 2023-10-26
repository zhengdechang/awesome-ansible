# awesome-ansible

使用 Ansible role ，一键部署 linux/ubuntu 系统常见服务及常见应用


## 实现的role如下

| role                            | example command 	      		    											| Comment                                                                                                             |
|---------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| docker roles        						| ansible-playbook -i environment/ setup_docker.yml  		| 安装docker和docker-compose                                                                                          |
| filebrowser roles   						| ansible-playbook -i environment/ deploy_filebrowser.yml   | 部署filebrowser，	FileBrowser是一个基于Web的文件管理器，它允许用户通过网络浏览、创建、编辑、上传、下载和删除文件。				 |
