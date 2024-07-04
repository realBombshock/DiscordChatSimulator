Discord Chat Simulator
======================

This repository contains code that produces a fake discord conversation
between multiple people. It takes in a text file of the form

::

   Jim:
   Hey Bob
   What kind of chocolate...
   Do you find in airports?

   Bob:
   idk Jim
   what kind?

   # this line is ignore becaused it has a # sign
   Jim:
   plain

and produces a sequence of discord messages, like those found in Beluga
videos. Messages from the same person stack:
for example, in the chat above, the sequence of messages produced by the
first chats of Jim are “Hey Bob” then “Hey Bob (newline) What kind of
chocolate…” and then “Hey Bob (newline) What kind of chocolate…
(newline) Do you find in airports?”

To run:

1. use the Virtualenv with the name of VenvDiscordChatGen as Python interpreter so you don't need to download
the requirements! but if you want to use your own python version use ``pip install -r requirements.txt``
but remember this code only works in python 3.10 and 3.11 (i tested in 3.10) it will not work with 3.12!

2. Add all desired profile pictures to the ``profile_pictures/`` folder.

3. Inside the ``profile_pictures/`` folder,then update the ``profile_pic_dict.json``
with names (corresponding to the names inwhatever script txt file you want to convert)
and corresponding profile pictures.

4. Inside the repository folder, run ``python generate_chat.py``. It
will prompt you to choose a ``.txt`` file of a script like the ``Chat Example File.txts``
The images will be savedin a newly created ``chat/`` folder with the form ``007T.png`` where
the first 3 numbers represent the image number in the entire sequence
and the letter is the first letter of speakers name.

The file naming convention for saved ``.PNG`` chats is used because
videos (very likely) have less than 1000 messages and the three digits
allows for easy importing and sorting into a software like premiere pro.
