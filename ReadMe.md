Vundle on Windows
Different File Names
By default, Vim on Windows will still look for .vimrc and install to ~/.vim. This doesn't work perfectly on Windows as the files aren't hidden, but .gitignore files are used in the same manner fairly commonly. You could for example change .vimrc to _vimrc and .vim to vimfiles - this would then require a change to the example vimrc below.

If you don't make these changes you should now be done with the pre-requisites and can go back to the main Vundle README and make the required vimrc changes.

Additionally, if you've set %HOME% environmental variable to some directory, that's the directory vim will search as ~/, thus you have to put .vimrc file and ~/.vim folder under the directory or remove %HOME% from environmental variable settings to use %USERPROFILE% as default.

If you've renamed the .vimrc and .vim names, open the cmd prompt or git bash and execute the following lines. If you do not have gvim on your path, use vim instead.

cd %USERPROFILE%
git clone https://github.com/VundleVim/Vundle.vim.git %USERPROFILE%/.vim/bundle/Vundle.vim
gvim .vimrc
From here, go to step 3 in the quick start and copy the sample config of Vundle into the .vimrc file.

Go to line around 11 and change

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
to

set rtp+=$HOME/.vim/bundle/Vundle.vim/
call vundle#begin('$HOME/.vim/bundle/')