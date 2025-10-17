A single-page, one-column resume for software developers. It uses the base latex templates and fonts to provide ease of use and installation when trying to update the resume. The different sections are clearly documented and custom commands are used to provide consistent formatting. The three main sections in the resume are education, experience, and Skills.

### Source
Forked from https://github.com/sb2nov/resume

### Preview

![Resume Screenshot](/resume_preview.png)

### Build using Docker

```sh
# Generate PDF
docker build -t latex .
docker run --rm -i -v "$PWD":/data latex pdflatex vichita_fongmala_resume.tex

# Generate preview image (PNG) with white background
docker run --rm -v "$PWD":/data -w /data --entrypoint="" dpokidov/imagemagick \
  magick -density 300 vichita_fongmala_resume.pdf \
  -background white -alpha remove -alpha off \
  -quality 100 resume_preview.png
```

### License

Format is MIT but all the data is owned by Vichita Fongmala.
