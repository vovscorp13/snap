#Stop the service and move the validator file

  sudo systemctl stop nolusd
  cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
  
#Delete a folder

  rm -rf $HOME/.nolus/data
  
#Cloning a Snapshot

  git clone git clone https://github.com/vovscorp13/snap
  
# cloud (https://cloclo13.cloud.mail.ru/attach/nolus/nolus_01_03_23_17_56.tar.lz4)
  
#Unzip the snapshot to a folder

  tar -Ilz4 -xf nolus_01_03_23_17_56.tar -C $HOME/.nolus
  
#Move the validator file and start the service

  mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
  sudo systemctl start nolusd
  sudo journalctl -u nolusd -f --no-hostname -o cat
