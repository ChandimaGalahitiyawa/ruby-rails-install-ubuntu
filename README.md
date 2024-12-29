# ruby-rails-install-ubuntu

Step 1: Update Ubuntu
  
 
sudo apt update && sudo apt upgrade -y

Step 2: Install Prerequisites
  
sudo apt install -y build-essential curl git libssl-dev libsqlite3-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip nodejs

Step 3: Install Ruby 3.2.2
Install rbenv and ruby-build:
  
 
sudo apt install -y rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.  rc
echo 'eval "$(rbenv init -)"' >> ~/.  rc
source ~/.  rc
Install Ruby:
  
 
rbenv install 3.2.2
rbenv global 3.2.2
ruby -v

Step 4: Install SQLite 3.42.0
Download and Build SQLite:
  
 
wget https://www.sqlite.org/2023/sqlite-autoconf-3420000.tar.gz
tar -xvf sqlite-autoconf-3420000.tar.gz
cd sqlite-autoconf-3420000
./configure
make
sudo make install
sqlite3 --version

Step 5: Install Rails 7.0.4

gem install bundler
gem install rails -v 7.0.4
rails -v


Step 6: Install Git 2.41.0
Remove Older Git Versions:
  
 
sudo apt remove -y git
Download and Build Git:
  
 
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.41.0.tar.gz
tar -xvf git-2.41.0.tar.gz
cd git-2.41.0
make prefix=/usr/local all
sudo make prefix=/usr/local install
git --version
