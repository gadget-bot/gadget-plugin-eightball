# Gadget Plugin to add a Magic Eightball

This is a [Gadget](https://github.com/gadget-bot/gadget) plugin to allow shaking a magic eightball.

Note that Gadget -- and therefore any plugin for Gadget -- is still very much a **work in progress**, so please don't use it in production yet (or if you do, don't complain).

## How do I use this plugin?

In your `main.go` for using Gadget, your `main()` function should instruct you bot, which is created using `gadget.Setup()` needs to be instructed to `Router.AddMentionRoutes(eightball.GetMentionRoutes())`. This _usually_ looks like this:

```golang
package main

import (
	gadget "github.com/gadget-bot/gadget/core"
	eightball "github.com/gadget-bot/gadget-plugin-eightball"
)

func main() {
	// This is the Gadget bot
	myBot := gadget.Setup()

	// Add your custom plugins here
	myBot.Router.AddMentionRoutes(eightball.GetMentionRoutes())

	// This launches your bot
	myBot.Run()
}
```

## What can this plugin do?

In your chat, you can perform the following actions:

* `Will I ... ?` - Rolls [2d6](https://en.wikipedia.org/wiki/Dice_notation) and reports the results.
  * Aliases: `Can I ... ?`, `Am I ... ?`
  * Parameters: `...` above is any question you might want to ask, such as `Will I get rich?` where `...` is replaced with `get rich`.
