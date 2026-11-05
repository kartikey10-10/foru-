# A small note for Ananya

A static, dependency-free website. The `ak` virtual environment is included for running the local Python web server.

## Run it locally

From this folder, activate the environment and start Python's built-in web server:

```bash
source ak/bin/activate
python -m http.server 8000 --bind 0.0.0.0
```

On your own computer, open <http://localhost:8000>. Keep the terminal running while you use the site. Stop the server with `Ctrl+C`; leave the environment with `deactivate`.

## Let someone elsewhere access it

The local server alone is only reachable on your computer/network. For a short-lived share, use a trusted HTTPS tunnel service (for example, Cloudflare Tunnel or ngrok) to forward its public URL to port `8000`. Share the HTTPS link it gives you, and stop the tunnel when you are done. Avoid exposing port 8000 directly on your router. For a permanent public link, deploy the files to a static hosting service instead; no Python server is needed there.

## Deploy with GitHub Pages

The `.github/workflows/deploy.yml` workflow publishes `index.html` whenever you push to the `main` branch. After you create and push this folder to a GitHub repository, open **Settings → Pages** and set **Build and deployment → Source** to **GitHub Actions**. The first deployment will provide a `https://<account>.github.io/<repository>/` address.

The site is public to anyone with its link. The `0000` code is a playful front-end puzzle, not a privacy lock.
