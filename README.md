# What to do with a fresh clone?

1. Install Hugo Extended.
2. Setup SSH key
    a. Generate the key:
    > ssh-keygen -b 4096
    b. Set up in github: https://github.com/settings/ssh/new
3. Clone the git repository
    > git clone git@github.com:mirwasi/mirwasi.github.io.git
4. Setup theme submodules:
    > git submodule init && git submodule update

# How to run

```
hugo serve
```

