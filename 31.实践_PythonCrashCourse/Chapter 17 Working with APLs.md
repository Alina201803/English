### Working with APLS

```python
import requests

# Make an API call and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)
#Store API response in a variable.
response_dict = r.json()

#Process results.
print(response_dict.keys())


import requests

# Make an API call and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)
#Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

#Explore information about the repositories.
repo_dicts = response_dict['items']
print("Repositories returned:", len(repo_dicts))
#Examine the first repository.
repo_dict = repo_dicts[0]
print("\nKeys:", len(repo_dict))
for key in sorted(repo_dict.keys()):
    print(key)
Status code: 200
Total repositories: 2800318
Repositories returned: 30

Keys: 73
archive_url
archived
assignees_url
blobs_url
branches_url
clone_url
collaborators_url
comments_url
commits_url
compare_url
contents_url
contributors_url
created_at
default_branch
deployments_url
description
downloads_url
events_url
fork
forks
forks_count
forks_url
full_name
git_commits_url
git_refs_url
git_tags_url
git_url
has_downloads
has_issues
has_pages
has_projects
has_wiki
homepage
hooks_url
html_url
id
issue_comment_url
issue_events_url
issues_url
keys_url
labels_url
language
languages_url
license
merges_url
milestones_url
mirror_url
name
node_id
notifications_url
open_issues
open_issues_count
owner
private
pulls_url
pushed_at
releases_url
score
size
ssh_url
stargazers_count
stargazers_url
statuses_url
subscribers_url
subscription_url
svn_url
tags_url
teams_url
trees_url
updated_at
url
watchers
watchers_count

working with the response dictionary
import requests

# Make an API call and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)
#Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

#Explore information about the repositories.
repo_dicts = response_dict['items']
print("Repositories returned:", len(repo_dicts))
#Examine the first repository.
repo_dict = repo_dicts[0]

print("\nSelected information about first repositiry:")
print('Name:',repo_dict['name'])
print('Owner:',repo_dict['owner']['login'])
print('Stars:',repo_dict['stargazers_count'])
print('Repository:',repo_dict['html_url'])
print('Created:',repo_dict['created_at'])
print('Updated:',repo_dict['updated_at'])
print('Description:',repo_dict['description'])

$ python 2018-07-11-1.py
Status code: 200
Total repositories: 2800333
Repositories returned: 30

Selected information about first repositiry:
Name: awesome-python
Owner: vinta
Stars: 52388
Repository: https://github.com/vinta/awesome-python
Created: 2014-06-27T21:00:06Z
Updated: 2018-07-11T13:30:36Z
Description: A curated list of awesome Python frameworks, libraries, software and resources
```

**今日所学**

requesting data using an API call

processing an API response

working with the response dictionary

