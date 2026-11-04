# Yankie-s-Birthday

## Birthday questionnaire

The questionnaire is on `next.html` and posts the ten mapped answers to the supplied Google Form using its `formResponse` endpoint. It uses a hidden iframe so visitors remain on the site.

The browser cannot verify that Google Forms accepted or saved a submission. The form therefore keeps the visitor's answers and reports this limitation rather than showing a definitive success message. After testing, confirm the test response appears in the Google Sheet linked to the form.

## Test locally

From the project directory, run:

```sh
python3 -m http.server 8000
```

Open `http://localhost:8000/next.html`, complete the required questions, and submit a clearly identifiable test response. Then check the linked Google Sheet. A browser message alone is not proof that the response was saved.

## Deploy on Vercel

1. Push this repository to GitHub.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Set **Framework Preset** to **Other** and the **Root Directory** to the repository root.
4. Leave the build and install commands empty. Set the **Output Directory** to `.` so Vercel serves the root-level HTML and assets.
5. Deploy. The site is static and needs no server, database, build step, or environment variables.
6. For later updates, push commits to the connected GitHub branch; Vercel will create deployments automatically.

Google Forms' `formResponse` endpoint is not a supported public API and may change. The front end has no credentials, but visitors' answers are sent directly to Google. If dependable confirmation is required, use a supported form provider or a carefully configured Google Apps Script endpoint.
