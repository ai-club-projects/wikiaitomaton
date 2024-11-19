# Как обновить units.aitomaton.online

проекты находятся в /home/asterisk/ (сорян за путаницу с путем, так сложилось)

## фронт
cd /home/asterisk/mui-app
git pull
npm install
npm run build

## back
cd /home/asterisk/server_py
git pull
sudo systemctl restart units

sudo journalctl -u units -f # посмотреть логи, убедиться что запуск успешен

