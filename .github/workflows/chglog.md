# name: Changelog

# on:
#   workflow_run:
#     workflows: ["Generate and Release"]
#     types:
#       - completed

# jobs:
#   build-chglog:
#     runs-on: ubuntu-latest
#     steps:
#       - name: Download artifact
#         uses: dawidd6/action-download-artifact@v2
#         with:
#           workflow: ${{ github.event.workflow_run.workflow_id }}
#           workflow_conclusion: success
#           name: tag-name-artifact

#       - name: Set tag_name from file
#         run: |
#           TAG_NAME=$(cat tag_name.txt)
#           echo "tag_name=$TAG_NAME" >> $GITHUB_ENV

#       - uses: actions/checkout@v4
#         with:
#           repository: ${{ github.repository }}
#           ref: refs/heads/main

#       - name: generate chglog
#         run: |
#           go install github.com/git-chglog/git-chglog/cmd/git-chglog@latest
#           export PATH=$PATH:$HOME/go/bin
#           git fetch --tags
#           git-chglog -c ${{ github.workspace }}/.chglog/config.yml -o CHANGELOG.md

#       - name: Upload asset to existing release
#         uses: softprops/action-gh-release@v1
#         with:
#           tag_name: ${{ env.tag_name }}
#           files: |
#             CHANGELOG.md
      
