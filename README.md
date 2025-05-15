# How to use this docker images

copy .env.example to .env then generate secret key and set it in .env WEBUI_SECRET_KEY as followings:

For Linux/macOS
```
openssl rand -base64 48
```

For Windows PowerShell
```
[Convert]::ToBase64String((1..48 | ForEach-Object {Get-Random -Maximum 256}) -as [byte[]])
```

Pull images.
```/bin/sh
docker compose pull
```

Run images.
```/bin/sh
docker compose up
```

Download the LLM model into the ollama image.

Following is the example to download gemma3:12b into ollama image.
```/bin/sh
docker exec -it ollama ollama pull gemma3:12b
```

Available LLM models are listed in [this page](https://ollama.com/library).

Once downloaded, you can open [http://localhost:3000](http://localhost:3000).

![Browser](https://raw.githubusercontent.com/kondonator/ollama-open-webui/images/screen.png)

All data is stored under ./docker/local/ollama and ./docker/local/open-webui.

Enjoy!
