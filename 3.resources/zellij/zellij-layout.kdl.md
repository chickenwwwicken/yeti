```
layout {
  default_tab_template {
    pane size=1 borderless=true {
      plugin location="zellij:compact-bar" 
    } // compact bar at top
  
    children // pain workin area

    pane size=2 borderless=true {
      plugin location="zellij:status-bar"
    } //bottom status bar
  }

  tab name="benji" {
    pane split_direction="vertical" {
      pane {
        cwd "/"
        command "nvim"
        args "."
        start_suspended true
      }
      pane split_direction="horizontal" {
        pane {
          cwd "~"
          command "nvim"
          args "."
          start_suspended true
        }
        pane {
          cwd "~"
        }
      }
    }
  }

  tab name="home" {
    pane split_direction="vertical" {
      pane {
        cwd "~"
        command "nvim"
        args "."
        start_suspended true
      }
      pane split_direction="horizontal" {
        pane {
          cwd "~"
          command "nvim"
          args "."
          start_suspended true
        }
        pane {
          cwd "~"
        }
      }
    }
  }

  tab name="config" {
    pane split_direction="vertical" {
      pane {
        cwd "~/.config"
        command "nvim"
        args "."
        start_suspended true
      }
      pane split_direction="horizontal" {
        pane {
          cwd "/"
          command "nvim"
          args "."
          start_suspended true
        }
        pane {
          cwd "~"
        }
      }
    }
  }

  tab name="$ssite" {
    pane split_direction="horizontal" {
      pane {
        // cwd "~/$cheats/$langs/$python/3ssite"
        // command "nvim"
        // args "."
        // start_suspended true
      }
      pane {
        // cwd "~/$cheats/$langs/$python/3ssite"
        // command "nvim"
        // args "."
        // start_suspended true
      }
    }
  }

  tab name="halfs" {
    pane split_direction="horizontal" {
      pane {
        cwd "~"
        command "nvim"
        args "."
        start_suspended true
      }
      pane {
        cwd "~"
      }
    }
  }
}
```
---
[[$zellij-guide]]
[[zellij-sidelayout.kdl]]