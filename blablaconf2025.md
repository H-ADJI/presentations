---
# theme: https://raw.githubusercontent.com/charmbracelet/glamour/refs/heads/master/styles/pink.json
author: Khalil Hadji
date: MMMM YYYY
paging: Slide %d of %d
---

# Terminal Multiplexers

Persistent Shell sessions + tilling panes + multi-windows navigation = Easy multi-tasking ( Assuming you work inside the terminal, the only and the superior way to do stuff ofc )

```


                                    ┌─────────────────────────────────────────────────────────────────────────────────────────────┌────────┐
                                    │                                                                                             │Session 1
                                    │                                                                                             └────────┘
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                             Pane 1                                                   │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    │                                                                                                      │
                                    ┼───────────────────────────────────────────────────┬──────────────────────────────────────────────────┼
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                    Pane 2                         │                      Pane 3                      │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    │                                                   │                                                  │
                                    └───────────────────────────────────────────────────┼──────────────────────────────────────────────────┘
```

## Disclaimer : I try to inject humor and ridiculousness in this presentation and all conversations i do. Please do not mistake my silliness for lack of seriousness and seriousness for lack of silliness, I barely know what i am talking about in most days. I am simply curious and i am hopping to understand what the hell is happening within this weird and wonderful peace of metal we call computers. If i say something stupid, as i always do, i can only promise to learn and improve.

---

# echo $(whoami)

- Studied Computer Science at **INPT**
- Wrote a lot of buggy code that never made it to a server
- Software Engineer at **Data Impact**
- Passionate about organized and low latency keyboard driven programming (who could've guessed)

---

# Table of Content

```







                                              +─────────────────────────────────────────────────────────────────────────────────────────+
                                              │                                                                                         │
                                              │          ┌──────────────────────────────────────┐                                       │
                                              │          │            Tarikh lyawm              │                                       │
                                              │          │                                      │                                       │
                                              │          │    1. Awalane kabira                 │                                       │
                                              │          │                                      │                 ***                   │
                                              │          │      2. taniyane saghira             │           ******* *****               │
                                              │          │                            \\        │          ** 0  ┴   0  **              │
                                              │          │                             \\\      │          *     ┴      **              │
                                              │          │                               \\\\   │          **    ┴┴     *               │
                                              │          │                                  \\\ │           ***       **                │
                                              │          └─────────────────────────────────────\\\            *********                 │
                                              │                                                  \\\              *                     │
                                              │                                                    \\\\          *****   ******         │
                                              │                                                        \\      *****  **  **            │
                                              │                                                          \******   *    ****            │
                                              │                                                                  ****                   │
                                              +─────────────────────────────────────────────────────────────────**──**──────────────────+
                                                                                                              **     **
                                                                                                            **        *
```

---

# Terminals

- A terminal is a GUI that allows you to insert shell's commands
- Terminals only display text ( Historically Ascii and now all kind of unicode sutff )
- Actually not only text but also images thanks to **Sixel** and **kitty graphical protocol**

```








                                                               """""
                                                             """   ""
                                                            """ "  " "
                                                           ""   "   "   ┌───────────┐          ┌───────────┐        ┌───────────┐
                                                            """    ""   │           │  Text    │           │  Sys   │           │
                                                              """""     │  Terminal ├─────────►│   Shell   ├───────►│     OS    │
                                                               """" ───►│           │ Commands │           │ Calls  │           │
                                                              " " """   │           │          │  >_ cmd   │        │           │
                                                                "       └───────────┘          └───────────┘        └───────────┘
                                                              """""        kitty                   Bash                Arch btw
                                                             "" ▲ ""       ghostty                 ZSH
                                                                │          Alacritty               Fish
                                                                │          ...                     ...
                                                        Average terminal
                                                              user
```

---

# What is a terminal multiplexers

Basically it lets you run multiple terminals in one terminal, for people that like the keyboard a lot.

```









                   ____                ______                    _             __               __         __                ____   ______                    _             __
                  / __ \____  ___     /_  _____  _________ ___  (_____  ____ _/ /    _____     / /  ____  / /______   ____  / __/  /_  _____  _________ ___  (_____  ____ _/ /
                 / / / / __ \/ _ \     / / / _ \/ ___/ __ `__ \/ / __ \/ __ `/ /    /____/    / /  / __ \/ __/ ___/  / __ \/ /_     / / / _ \/ ___/ __ `__ \/ / __ \/ __ `/ /
                / /_/ / / / /  __/    / / /  __/ /  / / / / / / / / / / /_/ / /    /____/    / /__/ /_/ / /_(__  )  / /_/ / __/    / / /  __/ /  / / / / / / / / / / /_/ / /
                \____/_/ /_/\___/    /_/  \___/_/  /_/ /_/ /_/_/_/ /_/\__,_/_/              /_____\____/\__/____/   \____/_/      /_/  \___/_/  /_/ /_/ /_/_/_/ /_/\__,_/_/


```

---

# Example of terminal multiplexers Software

- Zellij
  - ( + ) :
    - Modern implementation (Rust btw)
    - Default experience is acceptable
    - Cool name tbh
  - ( - )
    - configuration uses KDL, a sophisticated JSON clone (not turing complete 😔)
    - software in early stage == not very stable
- Tmux :
  - ( + ) :
    - Most popular multiplexer
    - Easy configuration and plugins using simple shell scripts
    - Docs are super detailed and easy to navigate
  - ( - ) :
    - Default experience is ugly and require some basic ricing
    - walo
- Screen :
  - ( + ) :
    - They call you grandpa
  - ( - ) :
    - They call you grandpa

---

# Core Concepts

```











                     _____                _                                  _       ___           __                                   ____
                    / ___/___  __________(_____  ____  _____                | |     / (_____  ____/ ____ _      _______                / __ \____ _____  ___  _____
                    \__ \/ _ \/ ___/ ___/ / __ \/ __ \/ ___/    ______      | | /| / / / __ \/ __  / __ | | /| / / ___/    ______     / /_/ / __ `/ __ \/ _ \/ ___/
                   ___/ /  __(__  (__  / / /_/ / / / (__  )    /_____/      | |/ |/ / / / / / /_/ / /_/ | |/ |/ (__  )    /_____/    / ____/ /_/ / / / /  __(__  )
                  /____/\___/____/____/_/\____/_/ /_/____/                  |__/|__/_/_/ /_/\__,_/\____/|__/|__/____/               /_/    \__,_/_/ /_/\___/____/



```

---

# Architecture

```
                                                         ┌──────────────────────────────────────────────────────────────────────────────────┐
                                                         │  ┌───────────────────────────────────────────────────────────────────────────┐   │
                                                         │  │                         ┌─────────────────────────────────────────┐       │   │
                                                         │  │                         │ ┌───────────────────────────────────────│─┐     │   │
                                                         │  │                         │ │  ┌────────────────────────────────────│─│──┐  │   │
                                                         │  │                         │ │  │                                    │ │  │  │   │
                                                         │  │                         │ │  │                                    │ │  │  │   │
                ┌─────────┐                 Session 1    │  │                         │ │  │                                    │ │  │  │   │
                │         │             ┌────────────────│─►│       windows   ──────► │ │  │                                    │ │  │  │   │
Process 1────►  │         │             │                │  │     (not the OS)        │ │  │                                    │ │  │  │   │
                │         │             │                │  │                         │ │  │                                    │ │  │  │   │
                │         ├─────────────┘                │  │                         └─────────────────────────────────────────┘ │  │  │   │
                │         │                              │  │                           └─────────────────────────────────────────┘  │  │   │
Process 2────►  │  TMUX   │                              │  │                              └─────────────────────────────────────────┘  │   │
    .           │  Server │                              │  └───────────────────────────────────────────────────────────────────────────┘   │
    .           │         ├─────────────┐                │   ┌─────────────────────────────────────────────────────────────────────────┐    │
    .           │         ┼             │                │   │                                                                         │    │
Process N────►  │         │             │  Session 2     │   │             ┌───────────────────────────┬─────────────┬─────────────┐   │    │
                │         │             └────────────────│─► │             │                           │             │             │   │    │
                │         │                              │   │             │                           │   Pane 2    │    Pan 4    │   │    │
                └─────────┘                              │   │             │                           │             │             │   │    │
                                                         │   │             │                           │             │             │   │    │
                                                         │   │window ─────►│       Pane 1              ┼─────────────┴─────────────┼   │    │
                                                         │   │             │                           │                           │   │    │
                                                         │   │             │                           │                           │   │    │
                                                         │   │             │                           │          Pane 3           │   │    │
                                                         │   │             │                           │                           │   │    │
                                                         │   │             └───────────────────────────┴───────────────────────────┘   │    │
                                                         │   │                                                                         │    │
                                                         │   └─────────────────────────────────────────────────────────────────────────┘    │
                                                         │                                  TMUX Client                                     │
                                                         │                                                                                  │
                                                         └──────────────────────────────────────────────────────────────────────────────────┘
```

---

# Demo

```











                                                ____                          _______
                                               / __ \___  ____ ___  ____     /_  __(_)___ ___  ___     __  ______ _____ _____ ___  __
                                              / / / / _ \/ __ `__ \/ __ \     / / / / __ `__ \/ _ \   / / / / __ `/ __ `/ __ `/ / / /
                                             / /_/ /  __/ / / / / / /_/ /    / / / / / / / / /  __/  / /_/ / /_/ / /_/ / /_/ / /_/ /
                                            /_____/\___/_/ /_/ /_/\____/    /_/ /_/_/ /_/ /_/\___/   \__, /\__,_/\__,_/\__,_/\__, /
                                                                                                    /____/                  /____/


```

---

# Final notes

## Thank you for listening

## Big thanks to Blablaconf for the opportunity

---

# Ressources and refrences

- You can find every thing in my github profile [@H-ADJI](https://github.com/H-ADJI)
  - [Presentation files :](url)
  - Presentation software : [slides](https://github.com/maaslalani/slides)
  - Screen keys software : [showmethekeys](https://github.com/AlynxZhou/showmethekey)
  - [my dotfiles github repo if you're looking for inspiration](https://github.com/H-ADJI/.dotfiles)
  - [Ascii art editora :](https://asciiflow.com/#/)
  - [ASCII art generator](https://patorjk.com/software/taag/)
