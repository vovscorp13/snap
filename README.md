                # 1 option
#Stop the service and move the validator file

      sudo systemctl stop nolusd
      cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
  
#Delete a folder

      rm -rf $HOME/.nolus/data
     
#Cloning a Snapshot

      git clone git clone https://github.com/vovscorp13/snap
  
  
#Unzip the snapshot to a folder

       lz4 -d nolus_01_03_23_17_56.tar.lz4 | tar -xv -C $HOME/.nolus
  
#Move the validator file and start the service

       mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
  
       sudo systemctl start nolusd
  
       sudo journalctl -u nolusd -f --no-hostname -o cat
     
 # 2 option     (windows-server)
 
 #Install WinSCP on a local PC (https://winscp.net/eng/download.php) 
 
 #Download the file from the cloud (https://cloclo13.cloud.mail.ru/attach/nolus/nolus_01_03_23_17_56.tar.lz4)
 
 #Connect to the server via WinSCP and download the downloaded file to home directory
 #In server stop the service and move the validator file

      sudo systemctl stop nolusd
      cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
  
#Delete a folder

      rm -rf $HOME/.nolus/data
      
#Unzip the snapshot to a folder

       lz4 -d nolus_01_03_23_17_56.tar.lz4 | tar -xv -C $HOME/.nolus
  
#Move the validator file and start the service

       mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
  
       sudo systemctl start nolusd
  
       sudo journalctl -u nolusd -f --no-hostname -o cat
 
     
     
