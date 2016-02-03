# Using Ansible to Orchestrate Chef

This is a hardcoded ansible play that uses Berkshelf and Chef Zero to Converge an EC2 Instance

## Things you need to change in this play to make it work

1.  Change the keypair value to a keypair that is installed on your ansible system
2.  Change the vpc_id to one of yours
3.  Change the subnet_id to one of yours
4.  Change the hosted_zone to one of your route53 hosted zones
5.  Change the friendly_cidr, make sure it includes the ip of the machine you are on

Other things you might need to do if you havent already:

1.  install ansible and boto
2.  configure your aws secret and key into either the awscli config or boto config
3.  install ChefDK with Berkshelf
4.  create an ansible inventory file (touch /tmp/inventory for example)

Simply run the play

 > ansible-playbook jenkins_play.yml -i /tmp/inventory

To clean up after you are done

  > ansible-playbook cleanup.yml -i /tmp/inventory
