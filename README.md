name: Deploy to WordPress

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Deploy to WordPress
      uses: rtCamp/action-wordpress-deploy@v2
      with:
        server: ${{ secrets.WP_SERVER }}
        username: ${{ secrets.WP_USERNAME }}
        password: ${{ secrets.WP_PASSWORD }}
        path: /path/to/your/ittechniq.wordpress.com/