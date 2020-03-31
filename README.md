# gumble

gumble is a [Mumble](https://mumble.info/) client implementation in Go

## Sub-projects

- gumble ([docs](https://pkg.go.dev/github.com/scaredmushroom/gumble/gumble))
    - Client library
- gumbleopenal ([docs](https://pkg.go.dev/github.com/scaredmushroom/gumble/gumbleopenal))
    - [OpenAL](http://kcat.strangesoft.net/openal.html) audio system for gumble
- gumbleffmpeg ([docs](https://pkg.go.dev/github.com/scaredmushroom/gumble/gumbleffmpeg))
    - [ffmpeg](https://www.ffmpeg.org/) audio source for gumble
- gumbleutil ([docs](https://pkg.go.dev/github.com/scaredmushroom/gumble/gumbleutil))
    - Extras that can make working with gumble easier

## Example

```go
package main

import (
  "github.com/scaredmushroom/gumble/gumble"
  "github.com/scaredmushroom/gumble/gumbleutil"
)

func main() {
  gumbleutil.Main(gumbleutil.Listener{
    UserChange: func(e *gumble.UserChangeEvent) {
      if e.Type.Has(gumble.UserChangeConnected) {
        e.User.Send("Welcome to the server, " + e.User.Name + "!")
      }
    },
  })
}
```

## Related projects

- [barnard](https://github.com/scaredmushroom/barnard)
    - terminal-based Mumble client
- [piepan](https://github.com/scaredmushroom/piepan)
    - an easy to use framework for writing Mumble bots using Lua

## License

MPL 2.0

## Author

Tim Cooper (<tim.cooper@github.com/scaredmushroom>)
