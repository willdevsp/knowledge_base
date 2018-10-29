# DROOLS

## Deploy Drools to DEV

Use the following steps in order to compile and deploy DRL's into DEV environment.

1)  Please login into comp300 box.  
   
    ` ssh -l oracle comp300.acc.br `
   
2)  Go to rule repository directory.

    ` cd /domains/ruleRepository/<STORE_ID> `

3) Find the rule package that you want to change

    ` cd /packages/com.accurate.acec.ckout.payment `

4) Backup the DRL files that you want to change, this is a very important step because you may break them, make sure you have a working copy.   

5) Upload you DRL's files to this directory. (SFTP)

6) Compile

    ` /opt/oracle/dev/11gr1ps5/app/wls/scripts/soasuite/dev/runWLock.sh transferRules.UNILEVERCO /opt/oracle/dev/11gr1ps5/ruleRepository/transferRules.sh nc_e_ad clustere3 /opt/oracle/dev/11gr1ps5/ruleRepository /domains/localRuleRepository UNILEVERCO FULL `
   
   The script above will compile and also transfer the compiled DROOLS file to the comp301 box, after this step you need to login into comp301.acc.br and make sure the LATEST file is up-to-date.

    ` ssh -l oracle comp301.acc.br `   
    ` cd /opt/oracle/dev/11gr1ps5/localRuleRepository/<STORE_ID>/packages/com.accurate.acec.ckout.payment `   
    ` ls -lah `

