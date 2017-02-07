---
layout: default
---

## User Manual

### Known issues

* Behavior might be unpredictable on pages that define their own keyboard shortcuts.
* gleeBox won't search inside IFrames of a page.
* Some bookmarklets don't work well as `!commands`

### The Basics

#### General Keys

| `g` | Launch gleeBox (In input fields, `Alt / ⌥ + g`) |
| `.` | Launch tab manager (In input fields, `Alt / ⌥ + .`) (Chrome only)
| `Tab` | Move to the next selected element |
| `Shift + Tab` | Move to the previous selected element |
| `Enter` | Launch a link or execute a command |
| `Shift + Enter` | Launch a link in a new tab |
| `Esc` | Close gleeBox / Tab Manager |

#### Default behavior

When you enter any text, gleeBox will search for links on the current page whose text matches your query. If it finds any links, it will highlight them and you can scroll through them by pressing the `Tab` key. You can open a particular link by pressing `Enter`.

In case gleeBox doesn't find any links, when you press `Enter`, it will either search the text on a search engine, or if you enter a string matching a URL, gleeBox will take you to that page.

#### Tab Manager (only in Chrome)

This will be a list of the currently open tabs. You can start typing to filter through them. Move through them using `Tab` or `Arrow` Keys. Choose one and press `Enter` to go to that tab. You can close a tab by selecting it and pressing `c` or `Backspace`.

### Commands

#### ?scraper commands

Scraper commands let you select particular types of elements on the page. You can navigate the selected elements via the `TAB` key.

| `?h` | Select main (h1, h2 & h3) headings |
| `?img` | Select linked images |
| `??` | Select text input fields. Hit `ENTER` to give focus to the selected field. |
| `?a` | Select all links |

#### !page commands

These commands are used to take some action on the current page. Type in the command and press `ENTER` to run.

| `!read` | Transform the page for a better reading experience using the Readability project |
| `!shorten` | Shorten the URL of the current page using bit.ly |
| `!tweet` | Redirect to twitter.com with the URL of the current page in the text field |
| `!share` | `!share service` <br> Share the current page. Supported services include m(ail), g)mail, t(witter), fb/facebook and services listed [here](https://www.addthis.com/services){:target="_blank"}. |
| `!help` | Open the user manual (this page) |
| `!options` | Open the options page |
| `!inspect` | `!inspect xyz` <br> Search for links containing the text `xyz` and return the jQuery selector for it. |
| `!v` | Play / pause videos on YouTube |
| `!ext` | Open the extensions page in Chrome |
| `!down` | Open the downloads page in Chrome |
| `!<bookmark>` | Run matching bookmarklet. You can also save bookmarklets and then execute them as a page command. <br> For example, if you bookmark the Instapaper bookmarklet and rename its title to `later`, you can then run it by typing in `!later` in gleeBox and pressing `Enter`. |
| `!set` | `!set option = value` <br> Set an option value. |

#### :yubnub commands

Syntax is `:command` where command is a [YubNub](http://yubnub.org/) command. While using this command, `$` can be used to represent the URL of the current page. Examples:

| `:fbshare $` | Share the current page on Facebook |
| `:wp cricket` | Search Wikipedia for "cricket" |
| `:tube elvis` | Search Youtube for "elvis" |
| `:site2pdf $` | Get a PDF for the current page |
| `:tw gleebox` | Search Twitter for "gleebox" |

#### \*jQuery commands

Syntax is `*selector` where selector is a jQuery selector. Hitting `ENTER` will navigate across all elements that match the jQuery selector. Examples:

| `*a` | All links |
| `*h3, h4, h5` | h3, h4 and h5 headers |
| `*textarea` | All textareas |
| `**` | Do not try this at home. |

### Advanced

Use the Options page in Chrome and the Options panel in Firefox to customize gleeBox. You can customize the appearance (size, location, theme), shortcut key, switch features on and off, change the default search engine and lots more.

Advanced customizations include ESP mode and custom ?scraper commands.

#### ESP mode
ESP mode lets you define default jQuery selectors for specific pages, so that you can just hit `g` on the page to select the elements you always select. A combination of URL and jQuery selector for the ESP mode is called a vision. We've included two `visions` for Google and Bing search result pages, roll your own for your favorite websites.

You can also define an ESP vision for your site using the <meta> tag so that when a user opens gleeBox on your site, it is automatically executed.

Example:

`<meta name="gleebox-default-selector" content="li>h2>a, a:contains(Previous), a:contains(Next)" />`

#### Custom ?scraper commands
If you use a jQuery selector on several pages, create a custom ?scraper command for it instead of typing the entire selector out every time.
