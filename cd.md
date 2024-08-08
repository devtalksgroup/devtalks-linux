# Cd Command
`cd` is a shell built-in command and stands for "changes directory".

You can point to directories in two ways:
1. **Absolute Paths:** Like /home/devtalks/lpic1/lesson1
2. **Relative Paths:** Like lpic1/lesson1 In this case, we are not adding the / in the beginning so the bash will try to find lpic1 directory where we are (local / relative)

You can check your current working directory with the `pwd` command.

# Tips and Tricks

### Toggle Between Directories:
Use `cd -` to switch back to the previous directory.
```bash
cd /path/to/first-directory
cd /path/to/second-directory
cd -  # returns to /path/to/first-directory
```
### Go Home Quickly:
Use `cd ~` or just `cd` to return to your home directory.
```bash
cd ~  # or just: cd
```
### Move Up One Directory:
Use `cd ..` to move up one level.
```bash
cd ..      # moves up one directory level
cd ../../  # moves up two directory levels
```
### Navigate to Root:
Use `cd /` to go to the root directory.
```bash
cd /  # navigates to the root directory
```
### Visit Another User's Home:
Use `cd ~username` to access another user's home directory
```bash
cd ~ali  # navigates to Ali's home directory
```
### Leverage Tab Completion:
Type part of a directory name and press `Tab` to auto-complete it.
```bash
cd /usr/lo[Press Tab]  # auto-completes to /usr/local/
```
### Reuse Last Argument:
Use `cd !$` to reuse the last argument from the previous command.
```bash
echo /some/directory/path
cd !$  # equivalent to: cd /some/directory/path
```
### Quick Access with `CDPATH`:
Set `CDPATH` for quick navigation to frequent directories.
```bash
export CDPATH=.:~/projects:/var/log # seperated with colon
cd myproject  # jumps to ~/projects/myproject if it exists
```
**Note:** For persistent usage, you can add this to your `.bashrc` file.(use absolute path)
### Enable AutoCD for Implicit Navigation:
Use the `shopt` command to enable or disable automatic directory navigation without explicitly typing `cd`.
```bash
shopt -s autocd  # enable auto cd
/path/to/dir     # automatically navigates to /path/to/dir
shopt -u autocd  # disable auto cd
```
**Note:** For persistent usage, you can add this to your `.bashrc` file.
### Use Directory Stack:
Use `pushd` to save directories and `popd` to return.
```bash
pushd /path/to/directory1
pushd /path/to/directory2
popd  # returns to /path/to/directory1
```
# zoxide
Tired of typing out long directory paths over and over? Use [`zoxide`](https://github.com/ajeetdsouza/zoxide) it's a **smarter `cd` command**. It remembers the directories you visit most frequently, letting you "jump" to them with just a few keystrokes.
Check out this [YouTube video](https://youtu.be/aghxkpyRVDY?si=zhDbbU9XiAMtQm8D) for a great explanation of `zoxide`'s features.
