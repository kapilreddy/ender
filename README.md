# Ender

Ender is a tmux tool helps you manage pane configurations in a tmux window.

Ender is meant to be used in dev environment to fire up multiple things like watch processes, servers and log outputs in tmux.


## How does it work?

An Ender config file looks like this. Place it in your project directory.

```json
["h", ["v", "echo \"foo\"", "echo \"bar\""],
      ["v", "echo \"hello\"", "echo \"world\""]]
```

This would split windows in tmux which will look something like this.

     --------------------------------------------------
    | $: echo "foo"          | $: echo "hello"         |
    | foo                    | hello                   |
    | $:                     | $:                      |
    |                        |                         |
     --------------------------------------------------
    | $: echo "bar"          | $: echo "world"         |
    | bar                    | world                   |
    | $:                     | $:                      |
    |                        |                         |
     --------------------------------------------------


```json
["h", ["v", "echo \"foo\"", "echo \"bar\""],
      ["v", "echo \"hello\"", "echo \"world\""],
      "echo \"ender\""]
```

     --------------------------------------------------
    | $: echo "foo" | $: echo "hello"| $: echo "ender" |
    | foo           | hello          | ender           |
    | $:            | $:             | $:              |
    |               |                |                 |
     --------------------------------                  |
    | $: echo "bar" | $: echo "world"|                 |
    | bar           | world          |                 |
    | $:            | $:             |                 |
    |               |                |                 |
     --------------------------------------------------

## Installation

Add ender in your PATH.


### Setup

To start using ender make a config file. Check ender config examples and place it as .ender in your project directory.

### Good to go!

Run 'ender' in your project directory while in tmux.

To specify differnt config file use --config param.

## Future Improvements
* Divide panes in correct percentages.


Twitter: @[KapilReddy](http://twitter.com/kapilreddy "Twitter handle: Kapil Reddy")

Special thanks to @[Prajwalit](http://twitter.com/prajwalit "Twitter handle: Prajwalit") for intial idea.
