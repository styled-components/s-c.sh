# `s-c.sh`

The styled-components link shortener, based on [`netlify-shortener`](https://github.com/kentcdodds/netlify-shortener).

## How does it work?

Redirects are added to the `_redirects` file, which is automatically deployed to Netlify and handled by them.

### Adding new redirects

#### From the GitHub UI

[Edit the `_redirects` file](https://github.com/styled-components/s-c.sh/edit/master/_redirects) and add your redirect at the very top in the format `/<short>    https://link.com`. For example:

```sh
/medium    https://medium.com/styled-components
/css-prop   https://medium.com/styled-components/announcing-native-support-for-the-css-prop-in-styled-components-245ca5252feb
```

Now `s-c.sh/medium` will redirect to the styled-components Medium publication, and `s-c.sh/css-prop` to the CSS prop announcement post! :tada:

#### From the command line

You need to set up this repository locally to add new redirects:

1. Clone the repo with `git clone git@github.com:styled-components/s-c.sh`
2. Install the dependencies with `npm install` (or `yarn`)

Once you have the repo set up locally, you simply have to run one command to add a new shortcode:

```sh
npm run shorten <url> <slug>

# for example
npm run shorten https://styled-components.com/docs d # s-c.sh/d will redirect to the docs now
```

Note that you need to have **write access to the repository** to make this happen. If that is not the case, you'll need to fork the repo first and push to your fork before submitting a PR.

## License

This whole repository is licensed under the MIT license.