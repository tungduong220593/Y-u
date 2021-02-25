# Y-u
name: Create issue on commit on: - push jobs:   create_commit:     runs-on: ubuntu-latest     steps:     - name: Create issue using REST API       run: |         curl --request POST \         --url https://api.github.com/repos/${{ github.repository }}/issues \         --header 'authorization: Bearer ${{ secrets.GITHUB_TOKEN }}' \         --header 'content-type: application/json' \         --data '{           "title": "Automated issue for commit: ${{ github.sha }}",           "body": "This issue was automatically created by the GitHub Action workflow **${{ github.workflow }}**. \n\n The commit hash was: _${{ github.sha }}_."           }' \         --fail Quyền cho GITHUB_TOKEN

  "message": "Not Found",
  "documentation_url": "https://docs.github.comname: Create issue on commit
on:
- push
jobs:
  create_commit:
    runs-on: ubuntu-latest
    steps:
    - name: Create issue using REST API
      run: |
        curl --request POST \
        --url https://api.github.com/repos/${{ github.repository }}/issues \
        --header 'authorization: Bearer ${{ secrets.GITHUB_TOKEN }}' \
        --header 'content-type: application/json' \
        --data '{
          "title": "Automated issue for commit: ${{ github.sha }}",
          "body": "This issue was automatically created by the GitHub Action workflow **${{ github.workflow }}**. \n\n The commit hash was: _${{ github.sha }}_."
          }' \
        --fail
Quyền cho GITHUB_TOKEN
  "message": "Not Found",
  "documentation_url": "https://docs.github.com  
