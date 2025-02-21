# how to selfhost-ai🤖

I'm showing you how to install Ollama with a ChatGPT like UI called OpenWebUI.
Just copy the commands and enjoy your local AI.


-Ollama RAM or VRAM Requirements per Parameter:
```bash
  1.5B ≈ 3.5GB RAM
  7B ≈ 16GB RAM
  8B ≈ 18GB RAM
  14B ≈ 32GB RAM
  70B ≈ 161GB RAM
  671B ≈ 1342GB RAM
```


-Install Ollama:

  ```bash
  curl -fsSL https://ollama.com/install.sh | sh
  ```


-Pull Ollama Model:

  ```bash
  ollama pull llama3.2
  ```

-Set up Docker’s apt repository:

  ```bash
  sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$UBUNTU_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```

-Install Docker Engine:

  ```bash
  sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
  ```

-Verify Docker Installation:

  ```bash
  sudo docker run hello-world
  ```

-Install Openwebui:

  ```bash
  sudo docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

-Reboot and run the last Command again

-go in your Browser and go to: 
http://localhost:3000/

-create admin account

-go back in the terminal

-configure file:

  ```bash
  sudo nano /etc/systemd/system/ollama.service
  ```

-add at the bottom of Service the line:

  ```bash
  Enviroment=OLLAMA_HOST=0.0.0.0"
  ```

-press strg + o

-press enter

-press strg + x

-reload system configuration:

  ```bash
  sudo systemctl daemon-reload
  ```

-restart the ollama service:

  ```bash
  sudo systemctl restart ollama
  ```

-reboot

-enjoy your new ai-server






































