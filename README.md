
Liferay on TomCat on OpenShift
==============================

  Create OpenShift application gear
        rhc app create liferay jbossews-2.0 mysql-5.1 phpmyadmin-4 -g medium

  go into git source
        cd liferay

  add some more storage
        rhc cartridge storage jbossews-2.0 -a liferay --add 1

  add remote
	git remote add github -m master https://github.com/eformat/openshift-cartridge-liferay-tomcat

  merge it
        git pull -s recursive -X theirs github master

  deploy to openshift 
        git push

  wait a few minutes
  browse to
        http://liferay-<your domain>.rhcloud.com
	
  accept default config and you are logged in with
        test@liferay.com / test
