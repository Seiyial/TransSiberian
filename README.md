# TransSiberian

On 12th of June, a Monday, a peace summit between US and North Korea was held a few kilometres from my office. The Saturday before, I watched [this video](https://youtu.be/ZsHMHukIlJY) on coding practices such as indenting and spacing. I was writing a code snippet on my diary app that defaulted indentation to 3 tab spaces.

Then it came to me. I got to do 3 tab spaces, because my code feels cleaner **to me** that way. But that doesn't mean I'll force anyone else to enforce it. There's all this holy war going on about indentation and spacing and I shall not go into that. But I believe we can have peace and **adaptability**. We should be able to switch between everyone's coding styles because everyone has a different preference, in a way that doesn't break the code, our time, and most of our practices.

## Installation

#### npm
```bash
npm i -g trans-siberian
yarn global add trans-siberian

cd myApp
trans-siberian install
# generates a template .tssb.yml file
```

#### Config file
```yaml

styles:
	CURRENT:
		type: spaces
		spacing: 2

	my-style:
		type: tabs
		spacing: 3

	your-style:
		type: spaces
		spacing: 2

	john:
		type: tabs
		spacing: 4

	ruby-standard:
		type: spaces
		spacing: 2

files:
	include: src/js
	include: lib/
	exclude: src/js/node_modules
	# ...

```

#### Usage
```bash

tssb <target_style> [<filepaths>] [--from <current_style>]
# Specify a <current_style> if you are importing code of another style into your project. E.g. tssb ruby-standard my-style ./js/imported/component/**
# <filepaths> must start with `./` .

# E.g. Editing code in a ruby open source project
git clone https://github.com/my-name/my-fork
tssb my-style ./app/** --from ruby-standard
# edit the code ...
tssb ruby-standard ./app/** --from my-style
# git commit  ...
```
