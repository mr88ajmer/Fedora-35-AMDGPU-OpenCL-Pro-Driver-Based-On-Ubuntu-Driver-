Fedora 35 Драйвер AMDGPU OpenCL Pro (на основе драйвера Ubuntu)

Если вам нужно запустить OpenCL на AMD в Fedora, выполните следующие действия:

$ sudo dnf -y groupinstall 'RPM Development Tools'

$ rpmdev-setuptree

$ cd ~/rpmbuild/SOURCES

 &wget --referer https://support.amd.com/en-us/kb-articles/Pages/AMDGPU-PRO-Driver-for-Linux-Release-Notes.aspx https://drivers.amd.com/drivers/linux/amdgpu-pro-21.30-1290604-ubuntu-20.04.tar.xz

$ git clone https://github.com/mr88ajmer/Fedora-35-AMDGPU-OpenCL-Pro-Driver-Based-On-Ubuntu-Driver- amdgpu-pro-opencl

$ cd amdgpu-pro-opencl

$ rpmbuild -ba amdgpu-pro-opencl.spec

$ sudo dnf -y --nogpgcheck install ~/rpmbuild/RPMS/x86_64/amdgpu-pro-opencl-21.30.1290604-1.fc35.x86_64.rpm

Запустите программу,с помощью amdgprorun или полный путь к программе:

$ amdgporun clinfo

$ amdgporun clpeak

$ amdgporun blender

$ amdgporun darktable-cltest

$ amdgporun darktable

& /usr/bin/amdgporun /home/user/nanominer-*/nanominer

И тд ... Должно работать!
