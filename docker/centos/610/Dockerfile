
FROM centos:centos6.10

WORKDIR /mnt

# 拷贝必要的文件 
COPY . .

# 1.更换镜像源 
# 2.安装必要的依赖 
RUN buildDeps='git' \
    && ls /etc/yum.repos.d/ \
	&& mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak \ 
	&& cp /mnt/config/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo \ 
    && yum clean all \
	&& yum makecache \
    && yum -y update \
	&& yum install -y $buildDeps 