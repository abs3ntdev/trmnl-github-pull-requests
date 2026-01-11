# GitHub Pull Request Viewer

TRMNL extension to show open Pull Request on GitHub.

## Todo

[ ] Screenshot to be added to the readme
[ ] Request publication to the TRMNL extension marketplace
[ ] Add the plugin settings section
[ ] Add html itself


## Install

You can go to the following link to install this recipe: https://usetrmnl.com/recipes/?????/install
Or you can copy the files from the `src` folder zip it and add it manually.

## Views

| View            | File                     | Description                               |
| --------------- | ------------------------ | ----------------------------------------- |
| Full            | `full.liquid`            | Full screen display                       |
| Half Horizontal | `half_horizontal.liquid` | Half screen, landscape                    |
| Half Vertical   | `half_vertical.liquid`   | Half screen, portrait                     |
| Quadrant        | `quadrant.liquid`        | Quarter screen                            |
| Shared          | `shared.liquid`          | Contains shared variables for all screens |

## Local Development

First, start the docker development server:

```bash
docker-compose up -d
```

Then, you can edit the files in the `src` folder and see the changes reflected in your browser: http://localhost:8001

## License

![License](https://img.shields.io/badge/license-MIT-blue.svg)