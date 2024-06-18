# init.lua Repository

This is my Neovim config. I will be detailing every step and requirement so 
that I do not forget when porting this config elsewhere, or so others that want
to follow this setup know what to do.

## Making init.lua Itself 
Started off by making an init.lua in the ~/.config/nvim directory. Opened it
with Neovim and added the "require("mario")" line to get the require the 
future directory. Lastly added "print("Hello")" line in order to have that 
pop up every time neovim opens for now to make sure that requirements are being
called as they should be. I saved and did ":so"

## Making lua and lua/mario directory (and mario/lazy)
Made a directory "lua" then inside of that made a "mario" directory. Inside the
mario directory I made an init.lua file. Inside of that init.lua file I put
"require("mario.remap") because I am going to make a remap file inside of this
directory. I also put "print("Hello from mario")" in this file so that when
the require gets called we can see that it is working as intended. I saved the
file and did ":so". Then, I made a "remap.lua" file in the mario directory as
well. I went into the file and added "vim.g.mapleader = " "". This makes the
vim leader key the spacebar. After that I added the line
"vim.keymap.set("n", "<leader>pv", vim.cmd.Ex)". This makes it so I can go from
a file in neovim when in normal mode and do space + pv and I will go back
into the netrw. I saved the file and did ":so" to source it. After that,
I made a set.lua file in the lua/mario directory and added a bunch of lines
in it that are in the repo. These lines are for configuring how neovim
looks in terms of lines, the cursor, and more. Then, I made a lazy init file
in the same directory and I added the lazy nvim installation and the require
statement with a spec equaling the lazy directory that I will create in this
same directory. Then put the change detection statement. Lastly, make a 
directory in this one named "lazy". This is where my plugins will live. Make
sure to save and source the set and lazy init files.

## Adding Plugins to mario/lazy

First, I will add telescope which helps us find files because it is a fuzzy
finder. It is very handy. In the mario/lazy directory, make a file called
telescope.lua and copy what I have in the repo and paste in there. Save and
source the file and when you quit neovim and enter netrw again lazy will 
install telescope and it will work with the remaps and all that. 

Next, we will download the color theme we want neovim to use. I will probably
be using cattpuccin-macchiato. To set up the color theme make the colors.lua
file in the mario/lazy directory and paste what I have. If the background
ever goes back you can use :lua ColorMyPencils() to make it go back to normal.
Save and source the file then reopen neovim to have lazy install cattpuccin
and then the color theme will be set for good.

Then comes fugitive. I make a fugitive.lua file in the mario/lazy directory
and I paste in what I have in the repository. I then save and source and quit
neovim in order to install it.

After that comes treesitter. I make a treesitter.lua file in the mario/lazy
directory and I paste in what I have in the repo. I save, source, quit, and
reopen neovim so the changes come into effect. 

Next we will install harpoon. I make a harpoon.lua file in the mario/lazy
directory and I paste what I have in the repo. Save, source, quit, and reopen
neovim so that it installs and the changes come into effect.

Now comes undo tree. I make a undotree.lua file in the mario/lazy directory
and I paste what I have in the repo. Save, source, quit, and reopen
neovim so that it installs it and the changes come into effect.

Then, I make an init.lua file in the directory and I add what I have in the
repo. Save, source, quit, and reopen neovim so that installs the packages.

After that, I install snippets. I make a snippets.lua file in the same repo
and I paste in there what I have in the repo. I save, source, quit, and reopen
neovim and everything installs.

Then, we make our lsp config with an lsp.lua file in the same directory. I
paste what I have in the repo and paste it in that file and save source and 
reopen neovim so it all installs. Make sure to do ":Mason" when you reopen
to install the other servers that you will need like pyright, jdtls, etc.

After that, I install the vim-tmux-navigator. I make a file called vimtmuxnav
and I paste what I have in the file. Save, source, and reopen neovim to install
and have the changes go into effect.

Then, make lualine.lua file in the same directory. Follow that up by pasting
what I have in the repo and then saving, sourcing, and reopening neovim
for the changes to take place.

## Going back to lua/mario to add the rest of the remaps

Go back to the remaps.lua file in the lua/mario directory and add the remaps
from the repo into there. Save, source, and reopen neovim so the changes
take place. This should be it for now.
