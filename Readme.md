# Mac 환경 설정 자동화 (Brewfile 사용)

이 가이드는 macOS를 초기화한 후 Homebrew와 Brewfile을 이용하여 개발 환경을 자동으로 세팅하는 방법을 설명합니다.

## 1. Homebrew 설치

먼저, Homebrew가 설치되어 있지 않다면 아래 명령어를 터미널에서 실행하여 설치합니다.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

설치가 완료되면 Homebrew가 정상적으로 설치되었는지 확인합니다.

```sh
brew --version
```

## 2. Brewfile 다운로드

Brewfile을 이용하면 macOS에서 필요한 패키지, 애플리케이션, 개발 도구 등을 한 번에 설치할 수 있습니다. 

```sh
git clone https://your-repo-url.git ~/mac-setup
cd ~/mac-setup
```

(또는 직접 `Brewfile`을 다운로드할 수도 있습니다.)

## 3. Brewfile을 이용한 패키지 설치

Brewfile이 위치한 폴더에서 아래 명령어를 실행하면 모든 패키지가 자동으로 설치됩니다.

```sh
brew bundle --file=Brewfile
```

## 4. Oh My Zsh 및 Powerlevel10k 설정

Brewfile을 실행하면 `Oh My Zsh`와 `Powerlevel10k` 테마가 자동으로 설치됩니다. 설치 후 아래 명령어를 실행하여 `zsh`를 기본 쉘로 변경합니다.

```sh
chsh -s $(which zsh)
```

터미널을 다시 시작하면 `Powerlevel10k` 초기 설정 마법사가 실행됩니다. 설정을 완료하면 개발 환경이 완전히 준비됩니다.

## 5. 필수 플러그인 설치

추가로 설치된 `zsh` 플러그인을 활성화하려면 `~/.zshrc` 파일을 열고 다음 내용을 추가합니다.

```sh
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
  zsh-completions
)
```

설정을 적용하려면 다음 명령어를 실행하세요.

```sh
source ~/.zshrc
```

## 6. 환경 설정 완료

모든 설치가 완료되면 터미널을 다시 시작하고 환경이 정상적으로 동작하는지 확인하세요. 

```sh
zsh --version
git --version
node --version
```

이제 macOS 개발 환경이 완벽하게 설정되었습니다! 🎉
