# ChatGPT Telegram Bot

## Setup
1. Get your [OpenAI API](https://openai.com/api/) key

2. Get your Telegram bot token from [@BotFather](https://t.me/BotFather)

3. Edit `config/config.example.yml` to set your tokens and run 2 commands below (*if you're advanced user, you can also edit* `config/config.example.env`):
    ```bash
    mv config/config.example.yml config/config.yml
    mv config/config.example.env config/config.env
    ```

4. How to run/deploy

4a. Local **run**:

 - run command:
    ```bash
    docker-compose --env-file config/config.env up --build -d
    ```


4b. **Home version**
- Launch docker application
- Creating image and uploading it to DockerHub:
```bash
docker build -f Dockerfile_home -t maindian/meowgpt:home .
docker push maindian/meowgpt:home
```
- check actual status of this image and tag on dockerhub

!run next command on server!
- dl actual image from dockerhub:
```bash
docker pull maindian/meowgpt:home
```
- stop previous containers (docker ps + docker stop + docker rm)
- Building container based on images from DockerHub (described in yml-file):
```bash
docker-compose -f env_home/docker-compose_home.yml up --build -d
```
или так:
```bash
docker-compose -f env_home/docker-compose_home.yml --env-file env_home/config/config.env up --build -d
```

4c. **Office version**:
- Launch docker application
- Creating image and uploading it to DockerHub:
```bash
docker build -f Dockerfile_office -t maindian/meowgpt:office .
docker push maindian/meowgpt:office
```
- check actual status of this image and tag on dockerhub

!run next command on server!
- dl actual image from dockerhub:
```bash
docker pull maindian/meowgpt:office 
```
- stop previous containers (docker ps + docker stop + docker rm)
- Building container based on images from DockerHub (described in yml-file):
```bash
docker-compose -f env_office/docker-compose_office.yml up --build -d
```
или так:
```bash
docker-compose -f env_office/docker-compose_office.yml --env-file env_office/config/config.env up --build -d
```

on current VM (and check notes file on linux VM):
```bash
docker-compose -f office/docker-compose_office.yml --env-file office/config_office.env up --build -d
```

