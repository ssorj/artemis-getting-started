# Getting started with ActiveMQ Artemis

## Step 1: Install the broker

~~~ shell
curl -f https://raw.githubusercontent.com/ssorj/artemis-install-script/main/install.sh | sh
~~~

## Step 2: Install the AMQP command-line tools

~~~ shell
pip install -i https://test.pypi.org/simple/ ssorj-qtools
~~~

## Step 3: Start the broker

~~~ shell
artemis run
~~~

## Step 4: Create a queue

~~~ shell
artemis queue create --name greetings --address greetings --auto-create-address --anycast --silent
~~~

## Step 5: Send a message

~~~ shell
qsend amqp://localhost/greetings hello
~~~

## Step 6: Receive a message

~~~ shell
qreceive amqp://localhost/greetings --count 1
~~~

## Stopping the broker

~~~ shell
artemis stop
~~~
