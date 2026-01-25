# Dotfiles (Zsh + Oh My Zsh)

## Опис
Цей репозиторій містить конфігураційні файли для налаштування оболонки **zsh** разом із фреймворком **Oh My Zsh**.
Конфігурація включає набір плагінів, що значно підвищують швидкість роботи в терміналі (автодоповнення, підсвітка синтаксису, навігація).

## Вимоги
- Linux / macOS / WSL
- Встановлені `git` та `curl`

## Інструкція зі встановлення (Clean Install)

### 1. Встановлення Zsh
Встановіть оболонку та зробіть її основною:
```bash
sudo apt update && sudo apt install zsh -y
chsh -s $(which zsh)
```
(Після цієї команди може знадобитися перелогінитись, щоб зміни вступили в силу)
2. Встановлення Oh My Zsh
Bash
```bash
sh -c "$(curl -fsSL [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))"
```
3. Завантаження конфігурації (Dotfiles)

Клонуємо цей репозиторій та переходимо в нього:
```bash
git clone [https://github.com/misterpivo52/devops.git](https://github.com/misterpivo52/devops.git) ~/dotfiles-repo
cd ~/dotfiles-repo
```
4. Встановлення зовнішніх плагінів

Ці плагіни не йдуть у комплекті з OMZ, тому завантажуємо їх окремо:

zsh-autosuggestions:
```bash
git clone [https://github.com/zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) \
${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
zsh-syntax-highlighting:
```bash
git clone [https://github.com/zsh-users/zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) \
${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
5. Застосування налаштувань

Створюємо бекап старого конфігу (якщо є) та створюємо посилання на новий:
```bash
mv ~/.zshrc ~/.zshrc.bak
ln -s ~/dotfiles-repo/.zshrc ~/.zshrc
```
6. Фіналізація

Перезапустіть термінал або виконайте:
```bash
source ~/.zshrc
```
