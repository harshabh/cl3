//DOCKER////


sudo apt-get remove docker docker-engine
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install docker-ce
sudo docker run hello-world
sudo docker run -it ubuntu:14.04
lsb_release -a
exit


/// AWS ///

create bucket - (aws s3api create-bucket --bucket %s --region us-west-2)%(src)
delete bucket- (aws s3api delete-bucket --bucket %s --region us-west-2)%(src)
view buckets - aws s3 ls
view bucket contents - (aws s3 ls %s)%(src)
upload file - (aws s3 cp %s s3:/%s)%(src,dest)
download file - (aws s3 cp s3:/%s %s)(src,dest)
delete file - (aws s3 rm s3:/%s)%(src)

/// KVM ///

list - virsh -c qemu:///system list
install - "sudo virt-install -n "+name+" --os-type=linux ram="+size+" --vcpus=1 --disk path="+filename+",bus=virtio,size=10 --graphics spice --cdrom "+iso+""
destroy - "virsh destroy "+VMid
 

norvdbsgc
