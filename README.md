hipmsg
===========

Tweaks to hipchat-cli/hipchat_room_message. A simple api client in bash to push messages to a hipchat room.


    $ hipmsg -t <token> -r <131313> -f "Dog"
-----
Examples:

    $ cat message.txt | hipmsg -t <token> -r 1234 -f "System"
    $ hipmsg -t <token> -r 1234 -f "System" -m "restock the fridge"
    $ HIPCHAT_API_TOKEN=<token> hipgmsg -r 1234 -f "Monitoring System" -m "this is broken"
    $ hipmsg -t <token> -r 1234 -f 'foo' -l
    $ hipmsg -t <token> -r 1234 -f 'foo' -k 100 -p 'listen ' -m 'this will be snipped to 100 chars' -s ' ok'


Usage:

    Usage: ./hipmsg -t <token> -r <room id> -f <from name>

    This script will send a message to the given room as
    a system message. If -m is not specified it will read from STDIN.

    REQUIRED OPTIONS:
    -t <TOKEN>      API token
    -r <ROOM_ID>    Room ID
    -f <FROM>       From name

    OPTIONS
    -h              Show this message
    -n              Trigger notification for people in the room
    -l              Instead of posting a message, give a list of rooms
    -m <MESSAGE>    Message string to post, overrides <stdin>
    -s <SUMMARY>    Optional Summary to append to message text
    -p <PRESUMMARY> Optioanl Summary to prepend to message text
    -o <HOST>       API host, defaults to api.hipchat.com
    -c <COLOR>      Message color (yellow, red, green, purple or random - default: yellow)
    -k <TRUNcATE>   Truncate the MESSAGE length to INT. does not affect SUMMARY or PRESUMMARY

    ENV VARIABLES
    HIPCHAT_API_TOKEN   Will be used instead of -t if set



[hc]: http://www.hipchat.com
