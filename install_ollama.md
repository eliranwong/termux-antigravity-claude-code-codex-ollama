# Install Ollama

1. Install Ollama on Termux

```
pkg install ollama
```

2. Install Ollama inside Ubuntu environment

## Login Unbuntu Environment

For details, read [install_ubuntu.md](install_ubuntu.md).

```
ubuntu
```

```
# install ollama
curl -fsSL https://ollama.com/install.sh | sh
echo 'export OLLAMA_HOST=0.0.0.0' >> ~/.bashrc

## auto start ollama server
tee -a ~/.bashrc > /dev/null << 'EOF'

## ollama server
start_ollama() {
  echo "Starting Ollama server ..."
  nohup ollama serve &
}
## Check if Ollama server is already running
if ! pgrep -f "ollama serve" > /dev/null; then
  start_ollama
else
  echo "Ollama server is already running."
fi
EOF

# set up ollama
nohup ollama serve &
ollama signin
ollama pull glm-5.2:cloud
```

Remarks:

* After "ollama signin" is executed, copy the generated url to the mobile chrome browser, follow instruction to login, then go back to termux and check if it is logged in.