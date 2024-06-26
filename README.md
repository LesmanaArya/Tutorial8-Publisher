## Tutorial 8 Reflection
1. How many data your publisher program will send to the message broker in one
run? <br/>
= Publisher program akan mengirim 5 data message ke message broker dalam sekali run. Hal ini dapat dilihat di function main dimana terdapat 5 p.publish_event dimana setiap publish_event akan mengirim 1 UserCreatedEventMessage <br/>

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber
program, what does it mean? <br/>
= Subscriber dan Publisher sama-sama mengakses `amqp://guest:guest@localhost:5672` yang menandakan bahwa mereka sama-sama menggunakan protokol AMPQ dan message broker yang sama. Pesan yang dikirim oleh Publisher akan diterima oleh message broker untuk selanjutnya diteruskan ke Subscriber

## Starting up RabbitMQ
![RabbitMQ startup screenshot](img/RabbitMQscreesnhot.png)

## Showing message receiving between Subscriber and Publisher
![Message sending screenshot](img/messageReceiving.png)

## Sending message repeatedly and frequently
![Sending message repeatedly screenshot](img/sendingMessageRepeatedly.png)

Spike diatas bisa muncul karena kita mengirim data berkali-kali dengan cepat kepada Subscriber. Setiap kita menjalankan cargo run pada Publisher, ia akan membuat koneksi baru dan mengirim message ke Subscriber. Jika dalam waktu yang singkat kita terus mengirimkan data ke Subscriber, maka akan muncul spike akibat pembuatan koneksi dan pengiriman data yang tinggi ke Subscriber