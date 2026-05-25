# Connect Playwright to Xray Jira instance
This is a demo code. 
This code demonstrates how to connect Xray Cucumber to an automation tool using tools like Github Actions for CI/CD
We have used the Playwright automation tool for this purpose
Please note: The code uses Client ID and Client Secret to communicate with the XRAY JIRA instance related to your login.
These Client ID and secrets are stored in cloud_auth.json and called via import-cloud.sh
The import-cloud.sh is further refered to, based on the environment it is called, by the code in playwright.yml


    - name: Submit results to Xray
      if: success() || failure()
      env:
        CLIENT_ID: ${{ secrets.CLIENT_ID }}
        CLIENT_SECRET: ${{ secrets.CLIENT_SECRET }}
      run: bash ./import-cloud.sh
