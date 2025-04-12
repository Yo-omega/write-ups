first, we have an input place where anything you put there, will be found in /announce inside an `<h1>`.
when trying a simple text it prints the text, if the text is between `{{ X }}`, it does show only the `X` without `{{` and `}}`.

That means we have an SSTi.
so here we need to know which technology is used in the server to render content, I have worked before with Jinja (python), so I started with testing it.

we put {{ '2' * 2 }}, it shows '22', so it's definitely Jinja.

with this:

    {{ self.__init__.__globals__.__builtins__.__import__('os').listdir('.') }}

we get what files we have in the current directory.
in the results, we have a file named `flag`.

with this template, we get the content of the file `flag`:

    get_flashed_messages.__globals__.__builtins__.open("/flag.txt").read()

---
link to the CTF [here](https://play.picoctf.org/practice/challenge/492?category=1&page=1)
