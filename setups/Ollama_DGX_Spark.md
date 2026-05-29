# DGX Spark Ollama Setup

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

```bash
sudo mkdir -p /etc/systemd/system/ollama.service.d
printf '[Service]\nEnvironment="OLLAMA_HOST=0.0.0.0"\n' | sudo tee /etc/systemd/system/ollama.service.d/override.conf
sudo systemctl daemon-reload
sudo systemctl restart ollama
```

```bash
curl http://0.0.0.0:11434
```


