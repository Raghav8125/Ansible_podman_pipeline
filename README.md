# Ansible_podman_pipeline
1.Install jenkins
2.Install anisible in jenkins server

dev.inv (private ip of podman)

playbook (podman.yml)



1)In jenkins
2)Newitem -->ansiblepodmanJob ---> pipeline --->ok
3)configure  -->pipelinescript
              declerative pipeline 
                  -->git checkout (pipeline syntax generator, provide git credentials)
                  -->maven build 
                  -->Execute ansiblePlaybooK ( pipeline syntax-->ansibleplaybook
                                                                      -->Ansible tool-->ansible
                                                                                         Playbook file path in workspace
                                                                                            podman.yml
                                                                                         Inventory file path in workspace
                                                                                            dev.inv
                                                                                        SSH connection credentials
                                                                                            (.pem file key of dev server)
