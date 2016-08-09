

### Install on Docker

```
docker pull newcrawler/spider
docker run -itd -p 8500:8500 --name=newcrawler newcrawler/spider
docker logs -f newcrawler
```

	

### Startup

```
sh newcrawler/start.sh &
```
http://127.0.0.1:8500 
