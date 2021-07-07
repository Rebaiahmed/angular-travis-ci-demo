
Sample poc Angular with Travis-Ci and Github pages to explore the CI/CD

Demo : https://rebaiahmed.github.io/angular-travis-ci-demo/

Thanks for this yml configuration 

```
language: node_js
node_js:
  - "12.0"
dist: trusty
sudo: required


branches:
   only:
   - master
   - main
before_script:
    - npm install -g @angular/cli

script:
- ng lint
- npm run test-headless
- ng build --prod --base-href https://rebaiahmed.github.io/angular-travis-ci-demo

deploy:
  provider: pages
  skip_cleanup: true
  github_token: $GITHUB_TOKEN
  local_dir: dist/angular-travis-demo
  on:
    branch: main
```

