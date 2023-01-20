git config --global user.email "kapalkoko@gmail.com"
git config --global user.name "Oleksandr Kashuba"

TD=$(date +%x) #Date
TZ=$(date +%Z) #Time Zone
TH=$(date +%H) #Hours
TM=$(date +%M) #Min
TS=$(date +%S) #Sec
#BackupDir=$(find /home/kapalulz/jenkinsBackUp1/FULL-* -maxdepth 0 -type d) # Name of folder

#Achieve if needed {
#cd /home/kapalulz/jenkinsBackUp1/FULL-*/
#zip -r -s 90m /home/kapalulz/jenkinsBackUp1/jenkins_backup1.zip ./*
#cp -r /home/kapalulz/jenkinsBackUp1/jenkins_backup1.z* /var/lib/jenkins/workspace/BackUP/
#cd /var/lib/jenkins/workspace/BackUP/
#                  }
#zip -s 0 split-foo.zip --out unsplit-foo.zip
#unzip unsplit-foo.zip

mv /home/kapalulz/jenkinsBackUp1/FULL-* /home/kapalulz/jenkinsBackUp1/JenkinsBackup
sleep 10
cp -r /home/kapalulz/jenkinsBackUp1/JenkinsBackup /var/lib/jenkins/workspace/BackUP/
rm -r /home/kapalulz/jenkinsBackUp1/JenkinsBackup

git add .
git commit -am "$TD $TZ:$TH-$TM-$TS #$BUILD_NUMBER"
#git tag "$TD|$TZ-$TH-$TM-$TS"
