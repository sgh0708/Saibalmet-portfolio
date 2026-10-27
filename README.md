# Saibal Ghosh – Portfolio

Static portfolio site served by GitHub Pages: https://sgh0708.github.io/Saibalmet-portfolio/

| File | Purpose |
|---|---|
| `index.html` | The portfolio page, including the contact form |
| `resume.html` | Source for the resume PDF |
| `Saibal_Ghosh_Resume.pdf` | Resume offered by the "Download Resume" buttons |

## Contact form

The form posts to [FormSubmit](https://formsubmit.co), which emails each enquiry (name, email, opportunity type, message) to `saibal1379met@gmail.com`. The visitor's address is set as reply-to.

The first submission after publishing sends a one-time **activation email** from FormSubmit to that Gmail inbox. Click the link in it to activate the form. After activation, FormSubmit shows a random alias for your address. To keep your Gmail address out of the page source, replace the email in `CONTACT_ENDPOINT` in `index.html` with that alias.

## Regenerate the resume PDF

After editing `resume.html`, run this from the repository folder in PowerShell:

```powershell
$uri = "file:///" + (Resolve-Path resume.html).Path.Replace('\','/').Replace(' ','%20')
& "${env:ProgramFiles(x86)}\Microsoft\Edge\Application\msedge.exe" --headless=new --disable-gpu --no-pdf-header-footer --print-to-pdf="$PWD\Saibal_Ghosh_Resume.pdf" $uri
```
