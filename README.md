# URL-Parser
An extremely simple URL Parser I created from scratch with no assistance. This was a personal project. 


## I initially started my Python journey by using the Python IDLE to code, which was very useful. However, over time I realised that I had to switch to something more substantial, which is what I did with VS Code. It does make for a more useful and definitely easy on the eyes terminal.

### Note, this is very simple and would not work in a professional environment, but it was a test of my skills.


---------


def url_parser():

    ''' Take a string input and analyse it. If the end of the URL is .net (allowed) or .com(not)'''

    import re

    suffixes = ('.org', '.edu', '.tech', '.blog')
    Url = input('Please paste your URL: ')
    if Url.startswith('https') and Url.endswith('.com'):
        result = f'Although this is a secure connection, the URL is still not allowed:\n {Url}'
        print(result)
    elif Url.startswith('http') and Url.endswith('.com'):
        result = f'This is an insecure connection and a blocked URL type:\n {Url}'
        print(result)
    elif Url.endswith('.com'):
        result = f'This is a blocked URL type:\n {Url}'
        print(result)
    elif Url.endswith('.net'):
        result = f'This is an allowed URL type:\n {Url}'
        print(result)
    elif [suffix for suffix in suffixes if Url.endswith(suffix)]:
        result = f'These {suffixes} are all acceptable URL types:\n {Url}'
        print(result)
    elif re.search(r'\.[a-z]{2}$', Url):
        result = f'These seem like country-level top code domains:\n {Url}'
        print(result)
    else:
        return 'This is not applicable'


---------


Here as you can see, I slowly built on this to include more and more options so that it could become a functional script. 
The decision to use 'startswith' and 'endswith' was a functional one as I know that most URLs have this naming convention.

The two main highlights of this script are the:

List Comprehension - instead of using a 'for loop' within an 'if' statement, I opted for this for two reasons:
  This is more efficient than writing a full 'for loop'
  &
  I was practicing to use list comprehension within a script to cement my knowledge

Regex Query - This was a custom query that identifies if the input received does not match the criteria listed above and is a country-level top code. 


Evaluation:

For a first starter script that is pertinent to my career, done entirely myself, it's not too bad. On reflection, I think wrapping this in a while loop and adding some input validation would improve this script massively.
