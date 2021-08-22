# Contents

- [Alfred App](#Alfred App)
  - [Configuration](#Alfred App#Configuration)
  - [Snippets](#Alfred App#Snippets)
    - [Example snippets](#Alfred App#Snippets#Example snippets)
      - [Other useful snippets](#Alfred App#Snippets#Example snippets#Other useful snippets)
  - [Snippet Triggers](#Alfred App#Snippet Triggers)
  - [Search Bookmarks](#Alfred App#Search Bookmarks)

# Alfred App
* <a href="https://www.alfredapp.com/powerpack/" target="_blank">Alfred App</a> is a free app that boosts your efficiency with hotkeys, keywords, text expansion and more. Search your Mac and the web, and be more productive with custom actions to control your Mac.
* Alfred app has a paid feature called PowerPack. 
<a href="https://www.alfredapp.com/powerpack/" target="_blank">Alfred Powerpack</a> is a set of powerful features, built on top of the robust core Alfred application. It is flexible and integrated with macOS, use it to customise your Mac and make you more productive

## Configuration
* I use `<Ctrl-space>` to trigger Alfred App to open. This enables me to enter commands to do stuff faster
* I set my Alfred app to open on startup 

![IMG Alfred settings for triggering it to open](https://i.imgur.com/kCBNgRk.png)

## Snippets
* If you are typing the same stuff over and over use snippets. I used <a href="https://textexpander.com/" target="_blank">TextExpander</a>  but their upgrades and asking for more money bothered me so I switched to Alfred App and never looked back.

### Example snippets
* If I add markdown that shows a fragment of JavaScript I add this snippet that is triggered by typing the Keyword `!!jsa`

![IMG code fragment snippet](https://i.imgur.com/zU5hg6E.png)


* `{clipboard}` holds what is in your clipboard, so I copy a fragment of JavaScript code and use the trigger key and it will out put this:

```js
function sample(arr, req) {
        arr = arr.sort(()=>{ return 0.5 - Math.random() }) ;
        let i = 0,
            array = [];
        while (i < req) {
            array.push(arr[i])
                ++i
        }
        return array
    }
```


#### Other useful snippets
* The current date with `!now`` trigger

```
`{ - {date} - }`
```

* Add an external link in markdown that opens in a new tab, there is now native way to do this but if you use a standard HTML anchor tag it works as you expect 
  - The `{cursor}` is how you tell the snippet where to place your cursor after inserting the snippet
  
  ```
  <a href="{clipboard}" target="_blank">{cursor}</a>
  ```
  
## Snippet Triggers 
*  <a href="https://www.alfredapp.com/help/workflows/triggers/snippet/" target="_blank">Snippet Triggers</a>   This gives you the ability to pass your snippet an argument so I can add markdown code and pass the language I want the code snippet to be so the markdown syntax highlighter works as you would expect

* So when I type the snippet trigger keyword `\\code` Alfred window will pop up and I'll type in my language `HTML` and it will insert my HTML code fragment like this:

![IMG html code fragment in markdown](https://i.imgur.com/drkjOA7.png)

* Which will render like below: 

```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>

<p>My first paragraph.</p>

</body>
</html>

```

## Search Bookmarks
* <a href="https://www.alfredapp.com/blog/tips-and-tricks/search-browser-bookmarks-safari-chrome-in-alfred/" target="_blank">Search your Browser Bookmarks in Alfred</a>
* Set up a trigger to open with `bm` trigger (open Alfred and type `bm`) and then follow it with the name of your bookmark (you can search Chrome and Safari)
* Below is an image showing the configuration in Alfred App 
  
![IMG Alfred App bookmark config](https://i.imgur.com/5neJcM1.png)
