``` 
layout {
  default_tab_template{
    pane size=1 borderless=true {
      plugin location="zellij:compact-bar"
    } // bar at top
  
    children // pain workin area 
  
    pane size=2 borderless=true {
      plugin location="zellij:status-bar"
    } // bottom status bar
  }

  tab name="system" {
    pane split_direction="horizontal" {
      pane {
        command "btop"
        start_suspended true
      }
      pane {
        command "neofetch"
        start_suspended true
      }
    }
  }

  tab name="/" {
    pane split_direction="horizontal" {
      pane {
        cwd "/"
        command "nvim"
        args "."
        start_suspended true
      }
      pane {
        cwd "~"
        command "nvim"
        args "."
        start_suspended true
      }
    }
  }

  tab name="config" {
    pane split_direction="horizontal" {
      pane {
        cwd "~"
        command "nvim"
        args "."
        start_suspended true
      }
      pane {
        cwd "~/.config"
        command "nvim"
        args "."
        start_suspended true
      }
    }
  }
}
```