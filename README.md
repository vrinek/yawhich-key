# yawich-key

This repository is a work in progress

An universal which-key shortcut displayer inspired from emacs-which-key 

![preview](./docs/assets/yawhich-key.gif)

# Get started

### Shortcuts
Create two shortcuts with your favorite shortcut manager
```bash
bash ~/path/to/yawhich-key # for default commands
bash ~/path/to/yawhich-key --major #for application specific commands
```
#### i3

```
bindsym $mod+comma exec "bash ~/path/to/yawhich-key --major"
bindsym $mod+space exec "bash ~/path/to/yawhich-key"

```


###  minor mode (general short cut map)
`./yawhich-key`

Configure your custom commands inside `./layers/core.json` (core.json is the entry point by default) and chain them by calling `./yawhich-key layers/custom-layer.json`
(of course yawich-key is unixporn compliant and can be customized through pywal, themer, env variable)
```json
// foo.json
[
  {
    "name" : "+foo", // the '+' char indicate which key to use in the menu
    "command": "foo", // this will be eval
    "confirm": false // will ask for confirmation
  },
  {
    "name" : "+barmenu", // the '+' char indicate which key to use in the menu
    "command": "./yawhich-key layers/barmenu.json", // this will be eval
    "confirm": false // will ask for confirmation
  }
]
```


###  major mode (current window class specific)
`./yawhich-key --major` will search the matching window WM_CLASS in `layer/wm_class.json`
If nothing is found it will `notifiy-send an error`



# Limitation
- Not yet in config folder
- Cant use special keys like `space, esc, alt, meta...` only chars
- Cant use two same key in a same menu
- If you press a wrong secquence or delete the invisible character the match wont work. (every time you open yawhich-key an invisible character is inserted in the search and this is what allow me to match by only pressing one key)
- Cant go back

# Roadmap
- [x] Basic secquence key handling
- [ ] Configure through bash script or yaml with env var instead of json
- [x] App specific yawhich-key (priority for vscode)
- [ ] Easy sharing layers with community through gist upload commands (inspired by pet)
- [ ] Standalone program (not using rofi), handle special keys shortcuts

# Contributing
Any contribution is welcome, especially ideas of usefull shortcuts,
themes, tackling ongoing issues, security issues / fix !
