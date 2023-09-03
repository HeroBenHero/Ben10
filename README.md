# FODI - Fast OneDrive Index

**Description:** FODI (Fast OneDrive Index) is a serverless program that allows you to quickly list and index your OneDrive files and folders without the need for a server. It provides features such as lightning-fast listing, specific path selection, folder encryption, and seamless deployment, making it a versatile tool for managing your OneDrive content.

## Table of Contents
- [Overview](#overview)
- [Demo](#demo)
- [Features](#features)
- [Limitations](#limitations)
- [Updates](#updates)
- [Installation](#installation)

---

## Overview

FODI (Fast OneDrive Index) is a convenient solution for indexing and managing your OneDrive files and folders. It offers the following features:

### Features
1. **Lightning-Fast Listing**: FODI provides near-instantaneous listing of your OneDrive content, ensuring you can find what you need quickly.

2. **Specific Path Selection**: You can specify the path you want to display, making it easy to focus on specific folders or directories.

3. **Folder Encryption**: For added security, FODI allows you to encrypt specific folders. You can do this by adding a `.password` file within the folder with your desired password.

4. **Serverless Deployment**: FODI is designed to be deployed without the need for a dedicated server. You can use services like Cloudflare Workers and GitHub Pages to host the frontend and backend components.

5. **Preview Support**: FODI enables previews for basic text files, images, audio, video, and Office documents, enhancing your file browsing experience.

### Limitations
While FODI offers numerous advantages, it's important to be aware of its limitations:

1. **Simplicity**: The interface is straightforward but may be considered basic.

2. **Browser Compatibility**: FODI may not work optimally with Microsoft's Internet Explorer (IE) or UWP version of Microsoft Edge browsers.

3. **Large Folders**: It may not perform well when displaying folders with thousands of files.

## Demo

[View Demo](https://herobenhero.github.io/Ben10/)

## Updates

**2019.12.23**
- Improved speed.
- Added Cloudflare Workers backend.

**2019.12.07**
- Further speed improvements.
- Added Python 3.6 backend.

## Installation

To deploy FODI backend on Cloudflare:

1. Create a Cloudflare Workers instance.

2. Copy the contents of [index.js](https://github.com/HeroBenHero/Ben10/blob/master/back-end-cf/index.js) into your Cloudflare Workers instance.

3. Customize the following variables in the code:
   - `EXPOSE_PATH`: Specify the OneDrive folder name you want to list. Use `/` for the entire folder, or `/music`, `/video`, etc., for specific paths.
   - `ONEDRIVE_REFRESHTOKEN`: Replace with the refresh_token obtained following the instructions provided.

4. Fetch the refresh_token using the [provided link](https://logi.im/fodi/get-code/). Note that this link may be valid for only three months.

5. Log in to your OneDrive and authorize SCF to access your OneDrive.

6. You may encounter an error page, but continue clicking the link until you reach the "Get a refresh token" page.

7. Copy the entire `refresh_token` and save it in your Cloudflare Workers.

8. Deploy your workers with a customized name and make note of the workers' URL (e.g., https://ben10.herobenhero.workers.dev), which will be added to the front-end page.

To set up the front-end GitHub Page:

1. Fork the FODI project into your GitHub repository.

2. Edit the `front_end` page and change `SCF_GATEWAY` to your workers' address (e.g., https://ben10.herobenhero.workers.dev).

3. Publish the page, and you are ready to go. The web page URL will be something like: https://51sec.github.io/FODI/front-end/
