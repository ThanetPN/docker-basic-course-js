---
theme : "black"
transition: "slide"
highlightTheme: "monokai"
slideNumber: false
logoImg: "images/logo-igg.png"
title: "Docker basic course (JS Edition) - Part 2"
---

# Checkpoint

- [x] Container
- [x] Image
- [x] Dockerfile
- [x] Registry
- [x] Auto build with Github (Bonus!)

---

# Checkpoint

- [ ] Basic docker volume
- [ ] Docker multistage build
- [ ] Real-world example project
- [ ] Deploy container to Heroku (Bonus!)

---

## Lab 9. Create upload script image

```
docker build -t app-php:0.1 .
```

### Volume mount

```
docker run -d -p 80:80 app-php:0.1
```

```
docker run -P app-php:0.1
```

---

```
docker volume ls
```

```
docker volume inspect {{volumeId}}
```

---

### Bind mount

```
docker run -d -p 80:80 -v $(pwd)/files:/var/www/html/files app-php:0.1
```

- -v is a volume mounting `HOST DIRECTORY`:`CONTAINER DIRECTORY`.

---

## Lab 10. Golang api

```
docker build ???
```

```
docker run ???
```

```
docker images
```

---

### Let's build multistage

```
docker build -f Dockerfile.multi -t app-go:0.2 .
```

---

![Image](slides/images/03.04.png)

---


![Image](slides/images/03.05.png)

---


![Image](slides/images/03.06.png)

---


![Image](slides/images/03.07.png)

---

# Checkpoint

- [x] Basic docker volume
- [x] Docker multistage build
- [ ] Real-world example project
- [ ] Deploy container to Heroku (Bonus!)

---

## Real-world example project

![Image](https://miro.medium.com/max/4800/0*6T9WJA6nqmF-t2r1.gif)

[:Ref](https://medium.com/bb-tutorials-and-thoughts/dockerizing-vue-app-with-nodejs-backend-33645f0f50ec)

---

## [Github](https://github.com/nitipatl/vuejs-nodejs-example)

```
git clone https://github.com/nitipatl/vuejs-nodejs-example.git
```

---

```
docker build -t vue-node-image:0.1 .
```

---

```
docker run -it -p  3080:3080 --name vue-node-ui vue-node-image:0.1
```

---

# Checkpoint

- [x] Basic docker volume
- [x] Docker multistage build
- [x] Real-world example project
- [ ] Deploy container to Heroku (Bonus!)

---

## Deploy container to Heroku (Bonus!)

```
heroku login
```

```
heroku container:login
```

```
heroku create
```

---

### Push image to Heroku

```
heroku container:push web --app warm-dusk-59086
```

---

### Release app / run container 

```
heroku container:release web --app warm-dusk-59086
```

```
heroku open --app warm-dusk-59086
```

```
heroku logs --tail --app warm-dusk-59086
```

# Checkpoint

- [x] Basic docker volume
- [x] Docker multistage build
- [x] Real-world example project
- [x] Deploy container to Heroku (Bonus!)
- [ ] [Auto deploy with Github (Bonus!)](https://dev.to/heroku/deploying-to-heroku-from-github-actions-29ej)

---

## 12 Factors app

[Link](images/03.08.png)

---