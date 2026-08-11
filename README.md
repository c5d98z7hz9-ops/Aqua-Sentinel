# Notebook → Web App on Render (via GitHub)

## What's in this folder
- app.ipynb        — your notebook (replace with yours, keep the name, or update render.yaml)
- requirements.txt — Python packages Render will install (add anything your notebook imports)
- render.yaml      — tells Render exactly how to build and run it (no manual settings)

## Step 1 — Put it on GitHub (no command line needed)
1. Go to github.com → click "+" → New repository → name it (e.g. my-notebook-app) → Public → Create.
2. On the new repo page click "uploading an existing file".
3. Drag in ALL THREE files (app.ipynb, requirements.txt, render.yaml) → Commit changes.

## Step 2 — Deploy on Render
1. Go to render.com → sign up / log in with your GitHub account.
2. Click New + → Blueprint.
3. Pick your repository → Render reads render.yaml → click Apply / Deploy.
4. Wait for the build (2–5 min). Your app is live at https://<name>.onrender.com

## Replacing the sample with YOUR notebook
- Upload your .ipynb to the repo (Add file → Upload). If it isn't named app.ipynb,
  edit render.yaml and change "app.ipynb" in startCommand to your filename.
- Add every library your notebook imports to requirements.txt (one per line).
- Every commit to GitHub redeploys automatically.

## Notes
- Free tier sleeps after ~15 min idle; first visit after that takes ~30–60 s to wake.
- 512 MB RAM on free tier — load data from files in the repo or URLs, don't train big models.
- Want a fancier UI later? Convert to Streamlit and change the startCommand to:
  streamlit run app.py --server.port=$PORT --server.address=0.0.0.0
