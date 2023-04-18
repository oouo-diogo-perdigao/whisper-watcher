# Instalação:
-- verifique se o python 3.10 esta instalado e disponivel em suas variaveis de ambiente
- $ `py -3.10 -m venv .venv` -- crie um ambiente virtual com o python 3.10
- $ `.venv/Scripts/activate` -- Ative o ambiente virtual
- (.venv) `pip install -U openai-whisper` -- Instale o wisper
- (.venv) `pip install --upgrade --no-deps --force-reinstall git+https://github.com/openai/whisper.git` -- force a atualização a versão mais recente disponibilizada no git da open ai (opcional)
- instale o ffmpeg
  - on Ubuntu or Debian `$ sudo apt update && sudo apt install ffmpeg`
  - on Arch Linux `$ sudo pacman -S ffmpeg`
  - on MacOS using Homebrew (https://brew.sh/) `$ brew install ffmpeg`
  - on Windows using Chocolatey (https://chocolatey.org/) `$ choco install ffmpeg`
  - on Windows using Scoop (https://scoop.sh/) `$ scoop install ffmpeg`

## Rodar na GPU
Se quiser roldar o wisper na gpu (recomendado) você deve usar o comando `--device cuda` para isso siga os passos:
- (.venv) `pip3 uninstall torch`
- (.venv) `pip cache purge`
- (.venv) `pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu117`

# Comando
`whisper "audio.mp3" --model medium --task transcribe --language pt --device cuda`
