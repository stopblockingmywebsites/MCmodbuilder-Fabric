# ModBuilder 🛠️

> A GitHub Actions-powered build pipeline for packaging Minecraft mods — no local toolchain required.

---

## What is ModBuilder?

ModBuilder lets you compile and package your Minecraft mod entirely through GitHub. Just upload your source, trigger the workflow, and download a ready-to-use `.zip` containing both the main jar and sources jar.

---

## Prerequisites

- A GitHub account
- A fork of this repository
- Your mod source files zipped as `mod.zip`

---

## Usage

Follow these steps every time you want to build your mod:

### 1. Use the Repository Template

Click **Use this template** at the top-right of this page to create your own copy.

### 2. Switch to the Correct Branch

Each mod version or variant lives on its own branch. Make sure you're on the right one before uploading anything.

```
git checkout <your-branch>
```

Or switch via the GitHub branch selector dropdown on the web UI.

### 3. Upload Your Source Zip

Upload your mod source files and name the file exactly:

```
mod.zip
```

> ⚠️ The filename must be `mod.zip` — the workflow depends on this exact name.

### 4. Trigger the Build Workflow

1. Go to the **Actions** tab of your forked repo.
2. Select **Build Workflow** from the list on the left.
3. Click **Run workflow**.
4. Select your target branch from the dropdown.
5. Click the green **Run workflow** button.

### 5. Download Your Build

Once the workflow completes (usually a minute or two), navigate to the finished run. Under **Artifacts**, you'll find a `.zip` containing:

- `mod-<version>.jar` — the main mod jar
- `mod-<version>-sources.jar` — the sources jar

---

## File Structure Expectations

```
mod.zip
├── build.gradle
├── gradle.properties
└── src/
    └── main/
        ├── java/
        └── resources/
            └── fabric.mod.json
```

> Make sure your zip follows standard mod project conventions or the build may fail.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Workflow doesn't appear | Check that Actions are enabled in your fork's settings |
| Build fails immediately | Confirm your file is named exactly `mod.zip` |
| Wrong mod version built | Double-check you selected the correct branch when running the workflow |
| Artifacts missing after run | The workflow may have failed — check the logs for errors |

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## License

[GNU General Public License v3.0](LICENSE)
