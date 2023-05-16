
## Setup

- Install the requirements using the following commands

```shell
$ pip install -r requirements.txt
$ sudo apt-get install chromium-chromedriver
```

### Testing the Chatbot

In the ``config.yml`` change the ``type`` parameter to ``test`` and run the following command

```shell
$ python main.py
```

#### Example

You would get an interface in the terminal.

Here is an example of mental health chatbot which I trained on r/therapy, r/mentalhealth subreddit for 100 epochs:

![chat-example](https://github.com/Ar9av/transformer-nmt-chatbot/blob/master/resources/example.gif)



### Configuring the Training Parameters

Change the parameters in ``config.yml`` and change the ``type`` to ``train`` and run the following command.

```shell
$ python main.py
```

#### Custom Dataset

If you're using your **own custom dataset** keep it in the following format.

Change the parameter `reddit_data` in ``config.yml`` to `False`.

The training data should be inside the ``data`` folder.
The conversation data should be kept in 2 files ``train.to`` and ``train.from``.
Each line denotes the id of each 1-1 conversation in from and to form.
``train.from``:

```
Hey
How are you

```

``train.from``:
```
Hi
I am fine

```

### Train on Reddit's conversation threads

You can directly train it over reddit conversations just by providing the subreddits and number of pages for which you want the data.
You can configure this using ``config.yml`` and change the ``reddit_data`` to ``True``. You can mention the subreddits, pages, sorting criteria in ``reddit_config.yml``.

![reddit-config](https://github.com/Github-Aiko/Transformer-Chatbot/blob/master/Application/resources/reddit_config.png)

Change the ``type`` in ``config.yml`` to ``train`` and run the following command

```shell
$ python main.py

```

### Reddit Auto Reply Scripting

After training over a subreddit data, we can use the model to interference through the the comments and generate reply using `reddit_bot.py`


Configure the bot (app), user credentials in `reddit_credentials.yml`

```shell
$ python reddit_bot.py

```