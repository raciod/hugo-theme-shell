# Hugo Theme: Shell (Modernized Fork)
Terminal-like theme with selectable color schemes. Fully updated for modern Hugo compatibility.

![Screenshot](https://raw.githubusercontent.com/Yukuro/hugo-theme-shell/master/images/motion2.gif)

## Quick Deploy
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/Yukuro/hugo-theme-shell-example)   

## Features
- Terminal-like portfolio
- Selectable color schemes (Pre-bundled inside `assets/sass/`)
  - `monokai` (Molokai)
  - `dracula`
  - `gruvbox_dark` / `gruvbox_light`
  - `material`
  - `tender`
  - `powershell`
  - `ubuntu`
  - `retro`
- Minimal design
- Responsive
- [MathJax](https://www.mathjax.org/): Beautiful and accessible math in all browsers

## Requirements
- Hugo Version 0.85.0 up to **v0.162.0+**
    - **Hugo extended version is required**.

## Installation
### Using a Local Fork
Clone or add your fork directly into your project's `themes/` directory and reference it in your project's root `hugo.toml`:
```toml
theme = 'hugo-theme-shell'

```

### How to use theme

Configure your `hugo.toml` using one of the locally available style names from `assets/sass/`:

```toml
[Params.Terminal]
scheme = "monokai" # Choices: monokai, ubuntu, powershell, retro, etc.

```

#### Modernization Note

Legacy versions of this theme attempted to dynamically fetch external Gogh color schemes via a `getJSON` API call. This has been completely removed to ensure zero build crashes on modern Hugo compilation engines (v0.141.0+). All configuration themes must exist as physical files inside the `assets/sass/` folder.

## Configuration

Example setup in your root `hugo.toml`:

```toml
[Params]
  # Note: This is for the meta description, which is different from the "description" displayed in the terminal.
  description = "Jane Doe's Portfolio!"
  
  [Params.Terminal]
  # Note: color scheme
  scheme = "monokai"

  # Note: in terminal
  # [userName]@[pcName]:~/$ cd [workDir]
  # [userName]@[pcName]:~/[workDir]$ cat [profile]
  #
  # [description]
  #
  # Note: if you set Params.Tree > use = true
  # [userName]@[pcName]:~/[workDir]$ tree ./[folderName]/
  # ./[folderName]/
  # ...
  userName = "jane"
  pcName = "laptop"
  workDir = "mydir"
  profile = "profile.txt"

  # Note: speed at which text is displayed on the terminal
  # Note: if set to 0, typing animation will be disabled
  ps1Delay = 0 # prompt speed : [userName]@[pcName]:~/$ , [userName]@[pcName]:~/[workDir]$
  stdoutDelay = 0 # stdout speed : [description] , files in Params.Tree
  commandDelay = 50 # command speed : cd [workDir] , cat [profile] , tree ./[folderName]/

  # Note: speed at which text is displayed on the activity pages
  titleDelay = 0 # title speed : "title" in front matter
  contentDelay = 0 # content speed : content in .md file

  description = """
  Hi I am Jane Doe!
  Nice to meet you!
  """

  [Params.Tree]
  use = true
  folderName = "my_activity"
  # Note: ["ACTIVITY", "URL or PATH TO YOUR MARKDOWN FILE"]
  files = [ 
    ["C/C++", "[https://www.example.com/](https://www.example.com/)"],
    ["Python", "[https://www.example.com/](https://www.example.com/)"],
    ["Go", "[https://golang.org/](https://golang.org/)"],
    ["Hugo", "/post/some-activity.md"],
  ]

```

## Troubleshooting

* **ToCSS Failure:** Fixed. Legacy `resources.ToCSS` implementations have been fully migrated to modern `css.Sass` pipeline declarations.
* **Partial Path Errors:** Fixed. The redundant `partials/` lookups within layout hooks have been streamlined to natively adhere to modern template mapping.

## Credits & Contributions

* Original Theme Creator: [Yukuro](https://github.com/Yukuro)
* Modernization & Asset Pipeline Migration: Assisted by AI (Gemini) to fix building issues on modern Hugo engines.


