pipeline {
agent {
label {
label "built-in"
customWorkspace "/mnt/repo-3/"
}
}
stages {
stage ("delete") {
steps {
sh "rm -rf /mnt/repo-3/pipelinerepo3-webhook"
}
}
stage ("git-clone") {
steps {
sh "git clone https://github.com/manali2006/pipelinerepo3-webhook.git"
}
}
stage ("httpd") {
steps {
sh "yum install httpd -y"
sh "service httpd start"
}
}
stage ("deploy") {
steps {
sh "cp -r /mnt/repo-3/pipelinerepo3-webhook/index.html /var/www/html"
sh "chmod -R 777 /var/www/html/index.html"
}
}
}
}

