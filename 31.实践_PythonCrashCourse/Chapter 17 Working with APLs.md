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



2018-07-12

**今日所学**

```python

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

print("\nSelected information about each repository: ")
for repo_dict in repo_dicts:
    print('\nName :', repo_dict['name'])
    print('Owner:', repo_dict['owner']['login'])
    print('Stars:',repo_dict['stargazers_count'])
    print('Repository:',repo_dict['html_url'])
    print('Description:',repo_dict['description'])

Status code: 200
Total repositories: 2803737
Repositories returned: 30

Selected information about each repository:

Name : awesome-python
Owner: vinta
Stars: 52430
Repository: https://github.com/vinta/awesome-python
Description: A curated list of awesome Python frameworks, libraries, softwad resources

Name : youtube-dl
Owner: rg3
Stars: 39607
Repository: https://github.com/rg3/youtube-dl
Description: Command-line program to download videos from YouTube.com and ovideo sites

Name : public-apis
Owner: toddmotto
Stars: 39344
Repository: https://github.com/toddmotto/public-apis
Description: A collective list of public JSON APIs for use in web developme

Name : models
Owner: tensorflow
Stars: 38151
Repository: https://github.com/tensorflow/models
Description: Models and examples built with TensorFlow

Name : flask
Owner: pallets
Stars: 37276
Repository: https://github.com/pallets/flask
Description: The Python micro framework for building web applications.

Name : thefuck
Owner: nvbn
Stars: 36180
Repository: https://github.com/nvbn/thefuck
Description: Magnificent app which corrects your previous console command.

Name : httpie
Owner: jakubroztocil
Stars: 36015
Repository: https://github.com/jakubroztocil/httpie
Description: Modern command line HTTP client ▒C user-friendly curl alternatith intuitive UI, JSON support, syntax highlighting, wget-like downloads, eions, etc.  https://httpie.org

Name : django
Owner: django
Stars: 35036
Repository: https://github.com/django/django
Description: The Web framework for perfectionists with deadlines.

Name : awesome-machine-learning
Owner: josephmisiti
Stars: 34073
Repository: https://github.com/josephmisiti/awesome-machine-learning
Description: A curated list of awesome Machine Learning frameworks, librarid software.

Name : requests
Owner: requests
Stars: 33476
Repository: https://github.com/requests/requests
        
  
making API Rate Limits
enter https://api.github.com/rate_limit 
{
  "resources": {
    "core": {
      "limit": 60,
      "remaining": 60,
      "reset": 1531407754
    },
    "search": {
      "limit": 10,
      "remaining": 10,
      "reset": 1531404214
    },
    "graphql": {
      "limit": 0,
      "remaining": 0,
      "reset": 1531407754
    }
  },
  "rate": {
    "limit": 60,
    "remaining": 60,
    "reset": 1531407754
  }
}

import requests
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

# Make an API call and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)
#Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

#Explore information about the repositories.
repo_dicts = response_dict['items']

names, stars = [],[]
for repo_dict in repo_dicts:
    names.append(repo_dict['name'])
    stars.append(repo_dict['stargazers_count'])

#Make visualization.
my_style = LS('#333366', base_style=LCS)
chart = pygal.Bar(style=my_style, x_label_rotation=45, show_legend=False)
chart.title = 'Most-Starred Python Projects on GitHub'
chart.x_labels = names

chart.add('',stars)
chart.render_to_file('python_repos.svg')
```

**今日所学**

summarizing the top repositories

monitoring apl rate limits

visualizing repositories using pygal 第一步



2018-07-13

**源代码**

```python
1.refining pygal charts
import requests
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

# Make an API call and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)
#Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

#Explore information about the repositories.
repo_dicts = response_dict['items']

names, stars = [],[]
for repo_dict in repo_dicts:
    names.append(repo_dict['name'])
    stars.append(repo_dict['stargazers_count'])

#Make visualization.
my_style = LS('#333366', base_style=LCS)

my_config = pygal.Config()
my_config.x_label_rotation = 45
my_config.show_legend = False
my_config.title_font_size = 24
my_config.label_font_size = 14
my_config.major_label_font_size = 18
my_config.truncate_label = 15
my_config.show_y_guides = False
my_config.width = 1000

chart = pygal.Bar(my_config, style=my_style)
chart.title = 'Most-Starred Python Projects on GitHub'
chart.x_labels = names

chart.add('',stars)
chart.render_to_file('python_repos.svg')

2.adding custom tooltips
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

my_style = LS('#333366', base_style=LCS)
chart = pygal.Bar(style=my_style, x_label_rotation=45, show_legend=False)
chart.title = 'Python Projects'
chart.x_labels = ['awesome-python','youtube-dl','public-apis']

plot_dicts = [
    {'value':52476, 'label': 'Description of awesome-python'},
    {'value':39640, 'label': 'Description of youtube_dl'},
    {'value':39397, 'label': 'Description of public-apis'}
    ]

chart.add('',plot_dicts)
chart.render_to_file('bar_descriptions.svg')


3.plotting the data
import requests
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

# Make an API call, and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)

# Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

# Explore information about the repositories.
repo_dicts = response_dict['items']

names, plot_dicts = [], []
for repo_dict in repo_dicts:
    names.append(repo_dict['name'])
    
    plot_dict = {
        'value': repo_dict['stargazers_count'],
        'label': repo_dict['description'],
        }
    plot_dicts.append(plot_dict)

# Make visualization.
my_style = LS('#333366', base_style=LCS)

my_config = pygal.Config()
my_config.x_label_rotation = 45
my_config.show_legend = False
my_config.title_font_size = 24
my_config.label_font_size = 14
my_config.major_label_font_size = 18
my_config.truncate_label = 15
my_config.show_y_guides = False
my_config.width = 1000

chart = pygal.Bar(my_config, style=my_style)
chart.title = 'Most-Starred Python Projects on GitHub'
chart.x_labels = names

chart.add('', plot_dicts)
chart.render_to_file('python_repos.svg')

```

**今日所学**

refining pygal charts

adding custom tooltips

plotting the data



2018-07-14

**源代码**

```python
adding clickable links to our graph
import requests
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

# Make an API call, and store the response.
url = 'https://api.github.com/search/repositories?q=language:python&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)

# Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

# Explore information about the repositories.
repo_dicts = response_dict['items']

names, plot_dicts = [], []
for repo_dict in repo_dicts:
    names.append(repo_dict['name'])
    
    plot_dict = {
        'value': repo_dict['stargazers_count'],
        **'label': repo_dict['description'],**
        'xlink': repo_dict['html_url'],
        }
    plot_dicts.append(plot_dict)

# Make visualization.
my_style = LS('#333366', base_style=LCS)

my_config = pygal.Config()
my_config.x_label_rotation = 45
my_config.show_legend = False
my_config.title_font_size = 24
my_config.label_font_size = 14
my_config.major_label_font_size = 18
my_config.truncate_label = 15
my_config.show_y_guides = False
my_config.width = 1000

chart = pygal.Bar(my_config, style=my_style)
chart.title = 'Most-Starred Python Projects on GitHub'
chart.x_labels = names

chart.add('', plot_dicts)
chart.render_to_file('python_repos.svg')

Status code: 200
Total repositories: 2198954
Traceback (most recent call last):
  File "2018-07-13-1.py", line 45, in <module>
    chart.render_to_file('python_repos.svg')
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\public.py", line 114, in render_to_file
    f.write(self.render(is_unicode=True, **kwargs))
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\public.py", line 52, in render
    self.setup(**kwargs)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\base.py", line 217, in setup
    self._draw()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\graph.py", line 933, in _draw
    self._plot()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\bar.py", line 146, in _plot
    self.bar(serie)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\graph\bar.py", line 116, in bar
    metadata)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\util.py", line 233, in decorate
    metadata['label'])
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pygal\_compat.py", line 61, in to_unicode
    return string.decode('utf-8')
AttributeError: 'NoneType' object has no attribute 'decode'

 the hackers news API 
import requests

from operator import itemgetter

# Make an API call, and store the response.
url = 'https://hacker-news.firebaseio.com/v0/topstories.json'
r = requests.get(url)
print("Status code:", r.status_code)

# Process information about each submission.
submission_ids = r.json()
submission_dicts = []
for submission_id in submission_ids[:30]:
    # Make a separate API call for each submission.
    url = ('https://hacker-news.firebaseio.com/v0/item/' +
            str(submission_id) + '.json')
    submission_r = requests.get(url)
    print(submission_r.status_code)
    response_dict = submission_r.json()
    
    submission_dict = {
        'title': response_dict['title'],
        'link': 'http://news.ycombinator.com/item?id=' + str(submission_id),
        'comments': response_dict.get('descendants', 0)
        }
    submission_dicts.append(submission_dict)
    
submission_dicts = sorted(submission_dicts, key=itemgetter('comments'),
                            reverse=True)

for submission_dict in submission_dicts:
    print("\nTitle:", submission_dict['title'])
    print("Discussion link:", submission_dict['link'])
    print("Comments:", submission_dict['comments'])

```

**错题本**

```python
今天在Stack Overflow 里提问的adding clickable links to our graph 中的
AttributeError: 'NoneType' object has no attribute 'decode' 报错
结果在别人的问题下发现解决办法。。。。。
Try str() like above, it seems the data you got before hasn't clarifed the type of value that 'description' storged
'label': repo_dict['description'],改为str（repo_dict['description']）后成功
 然后这个图太棒了，能看到最受欢迎的project，点击柱状图，还能跳转到相应的github页面。
```

**今日所学**

adding clickable links to our graph

the hackers news API



2018-07-15

**今日所学**

```python
17-1 Other languages
import requests
import pygal
from pygal.style import LightColorizedStyle as LCS, LightenStyle as LS

# Make an API call, and store the response.
url = 'https://api.github.com/search/repositories?q=language:Java&sort=stars'
r = requests.get(url)
print("Status code:", r.status_code)

# Store API response in a variable.
response_dict = r.json()
print("Total repositories:", response_dict['total_count'])

# Explore information about the repositories.
repo_dicts = response_dict['items']

names, plot_dicts = [], []
for repo_dict in repo_dicts:
    names.append(repo_dict['name'])
    
    plot_dict = {
        'value': repo_dict['stargazers_count'],
        'label': str(repo_dict['description']),
        'xlink': repo_dict['html_url'],
        }
    plot_dicts.append(plot_dict)

# Make visualization.
my_style = LS('#333366', base_style=LCS)

my_config = pygal.Config()
my_config.x_label_rotation = 45
my_config.show_legend = False
my_config.title_font_size = 24
my_config.label_font_size = 14
my_config.major_label_font_size = 18
my_config.truncate_label = 15
my_config.show_y_guides = False
my_config.width = 1000

chart = pygal.Bar(my_config, style=my_style)
chart.title = 'Most-Starred Java Projects on GitHub'
chart.x_labels = names

chart.add('', plot_dicts)
chart.render_to_file('java_repos.svg')

17-2 Active Discussion
import requests

from operator import itemgetter

# Make an API call, and store the response.
url = 'https://hacker-news.firebaseio.com/v0/topstories.json'
r = requests.get(url)
print("Status code:", r.status_code)

# Process information about each submission.
submission_ids = r.json()
submission_dicts = []
for submission_id in submission_ids[:30]:
    # Make a separate API call for each submission.
    url = ('https://hacker-news.firebaseio.com/v0/item/' +
            str(submission_id) + '.json')
    submission_r = requests.get(url)
    print(submission_r.status_code)
    response_dict = submission_r.json()
    
    submission_dict = {
        'title': response_dict['title'],
        'link': 'http://news.ycombinator.com/item?id=' + str(submission_id),
        'comments': response_dict.get('descendants', 0)
        }
    submission_dicts.append(submission_dict)
    
my_style = LS('#333366')
my_config = pygal.Config()
my_config.x_label_rotation = 45
my_config.show_legend = False
my_config.truncate_label = 15
my_config.title_font_size = 24
my_config.label_font_size = 14
my_config.major_label_font_size = 18
my_config.show_y_guides = False
chart = pygal.Bar(my_config, style=my_style)
chart.title = "Most-active news on Hacker News"


chart.add('', submission_dicts)
chart.render_to_file('news.svg')

```

**今日所学**

练习