FROM node:8

WORKDIR /home

COPY . .

RUN cd renren-fast-vue && npm rebuild node-sass && npm install 

EXPOSE 8001

CMD cd renren-fast-vue && npm run dev
