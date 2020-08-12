# wizard_bot
GoogleDrive Fclone Java Telegram Bot

Depends on Java 1.8+  Redis 5.04+  MongoDB 4.0.17+

Step1. Setup Java Env(Google or other By urself)

Step2. Install Redis(make && make install)

Step3. Modify redis.conf these places as below:

      #bind 127.0.0.1
      protected-mode no
      daemonize yes
      logfile "xxxx.log"
      stop-writes-on-bgsave-error no
      
Step4. use command redis-server to start redis

U can choose local mongodb or mongodb atlas

Step5. Install MongoDB(Google or other By urself)

Step6. use command mongo to step into mongodb-cli and then

       use admin
       db.createUser({user:"admin",pwd:"admin",roles:["root"]})  //create admin
       db.auth("admin", "admin")          //check auth
       use wizard
       db.createUser({user: "wizard", pwd: "wizard", roles: [{ role: "dbOwner", db: "wizard" }]})
       
Step7. Install fclone(Google or other By urself) and setup by fclone config

Step8. wget https://github.com/swordman-sm/wizard_bot/releases/download/wizard_bot_v0.12_4/wizard_bot_v0.12_4.zip

Step9. unzip wizard_bot_v0.12_4.zip

Step10. modify config/config.properties as u like

If choose local mongodb：

       mongodb.connect.type=local
       mongodb.host=127.0.0.1
       mongodb.port=27017
       mongodb.username=wizard
       mongodb.password=wizard
       mongodb.database=wizard
       
If choose MongoDB Atlas modify

       mongodb.connect.type=atlas
       mongodb.host=cluster0.xxxx.gcp.mongodb.net
       mongodb.port=27017  //blank or not both ok
       mongodb.username=root
       mongodb.password=xxxxxxxx
       mongodb.database=wizard

Step11. use command sh restart.sh to start bot

Step12. if u want background this process pls use nohup screen or tumx .etc (If u can not understand what i say pls give up,becauz am lazy)
       
