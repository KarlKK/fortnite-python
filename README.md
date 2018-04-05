# fortnite-python
Python wrapper for http://fortnitetracker.com/ api.

## Installation

You can install it via pip

```
pip install fortnite-python
```


## Usage

You need to register for an api key at https://fortnitetracker.com/site-api

Then it's just easy as:

```
from fortnite_python import FORTNITE

fortnite = FORTNITE('Given api key')
```


Retrieving a player:

```
>>> from fortnite_python import FORTNITE

>>> fortnite = FORTNITE('Given api key')
>>> player = fortnite.player('playername')
player

<Player 20a8fafaa-6chfj-6455-b715-2424fff pc>

```

The default platform is PC, if you want to use a diferent platform you should
do it this way:

```
>>> from fortnite_python import FORTNITE
>>> from fortnite_python.domain import Platform

>>> fortnite = FORTNITE('Given api key')
>>> player = fortnite.player('playername', Platform.XBOX)
>>> player
<Player 20a8fafaa-6chfj-6455-b715-2424fff xb1>


```

You can check the available platforms [here](https://github.com/xcodinas/fortnite-python/blob/master/fortnite_python/domain.py#L4)


Retrieving player stats:


```
>>> from fortnite_python import FORTNITE
>>> from fortnite_python.domain import Mode

>>> fortnite = FORTNITE('Given api key')
>>> player = fortnite.player('playername')
>>> stats = player.getStats(Mode.duo)
>>> stats.wins
'10'
>>> stats.top3
'20'

```
You can check the available modes [here](https://github.com/xcodinas/fortnite-python/blob/master/fortnite_python/domain.py#L10)