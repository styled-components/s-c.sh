# `s-c.sh`

The styled-components link shortener, based on [`netlify-shortener`](https://github.com/kentcdodds/netlify-shortener).

## Adding a new short link

All you have to do to add a new short link is to [edit the `_redirects` file](https://github.com/styled-components/s-c.sh/edit/master/_redirects) and add your redirect at the very top in the format `/<short>    https://link.com`. For example:

```sh
/medium     https://medium.com/styled-components
/css-prop   https://medium.com/styled-components/announcing-native-support-for-the-css-prop-in-styled-components-245ca5252feb
```

Now `s-c.sh/medium` will redirect to the styled-components Medium publication, and `s-c.sh/css-prop` to the CSS prop announcement post!

:tada: :tada: :tada:

### From the command line

You can also use the `netlify-shortener` CLI locally to add new short links, which will make sure the `_redirects` file is in the right format. To do so, you need to set up this repository locally:

1. Clone the repo with `git clone git@github.com:styled-components/s-c.sh`
2. Install the dependencies with `npm install` (or `yarn`)

Once you have the repo set up locally, you simply have to run one command to add a new shortcode:

```sh
npm run shorten <url> <slug>

# for example
npm run shorten https://styled-components.com/docs d # s-c.sh/d will redirect to the docs now
```

> Note that you need to have **write access to the repository** for this to work. If that is not the case, you'll need to fork the repo first and push to your fork before submitting a PR.

## How does it work?

Redirects are added to the `_redirects` file, which is deployed to Netlify and handled by them. The `master` branch in this repo is always in sync with s-c.sh!

## License

This whole repository is licensed under the MIT license.
