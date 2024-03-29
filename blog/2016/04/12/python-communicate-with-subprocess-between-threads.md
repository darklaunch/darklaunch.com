# Python communicate with subprocess between threads

Use python subprocess to communicate between python scripts.

```python
# script.py
import subprocess

process = subprocess.Popen(
    ['python', 'my_other_script.py'], shell=False,
    stdin=subprocess.PIPE, stdout=subprocess.PIPE)
result = process.stdout.readline()
print(result)
```

```python
# my_other_script.py
print('hello, world!')
```

```bash
$ python script.py 
hello, world!

```

Here's an example game in which the player tries to guess the dealer's number.

```python
# Dealer (dealer.py)
import random
import sys

MIN_NUMBER = 1
MAX_NUMBER = 10

def main():
    while True:
        player_bet = int(sys.stdin.readline())
        if player_bet == 0:
            sys.stdout.write('Ok. Thanks for playing.\n')
            sys.stdout.flush()
            break
        number = random.randint(MIN_NUMBER, MAX_NUMBER)
        if player_bet == number:
            sys.stdout.write('number is {0}: player wins!\n'.format(number))
        else:
            sys.stdout.write('number is {0}: dealer wins\n'.format(number))
        sys.stdout.flush()

if __name__ == '__main__':
    main()
```

```python
# Player (player.py)
import random
import subprocess
import sys

import dealer

process = subprocess.Popen(
    ['python', 'dealer.py'], shell=False,
    stdin=subprocess.PIPE, stdout=subprocess.PIPE)

for i in xrange(8):
    bet = random.randint(dealer.MIN_NUMBER, dealer.MAX_NUMBER)
    sys.stdout.write('player betting {0}\n'.format(bet))
    process.stdin.write('{0}\n'.format(bet))
    result = process.stdout.readline()
    sys.stdout.write(result)

process.stdin.write('0\n')
result = process.stdout.readline()
sys.stdout.write(result)
```

```bash
$ python player.py 
player betting 4
number is 4: player wins!
player betting 2
number is 8: dealer wins
player betting 2
number is 6: dealer wins
player betting 1
number is 9: dealer wins
player betting 5
number is 7: dealer wins
player betting 1
number is 10: dealer wins
player betting 7
number is 7: player wins!
player betting 8
number is 3: dealer wins
Ok. Thanks for playing.
```

---

Posted Apr 12, 2016.

https://www.darklaunch.com/2016/04/12/python-communicate-with-subprocess-between-threads.html