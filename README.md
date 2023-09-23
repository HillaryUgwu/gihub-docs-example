# Wirting Good Documentation

## Step 1 - Using Codeblocks

Codeblocks in markdown make it *very easy* to tech people to **copy, paste, and share** codes. A good __Cloud Engineer__ uses codeblocks whenever possible.

It allows others to copy and paste their code while keeping the code clearly legible and easy to replicate or research / troubleshoot issues with no ambiguity.

- In order to create codeblocks in markdon, you need to use three backticks like this: `(```)`
- Not to be confused with quotation marks `(''')`
- And remember to wrap your code ~(start and end)~ with the 3 backticks.
- See example below with an optional syntax highlighting as python:
```python
from flask import Flask, render_template_string
app = Flask(__name__)

# Function to calculate square
def square(number):
    return number ** 2

@app.route("/")
def home():
    # Variable assignment
    greeting = "Hello, World!"
    integer = 10
    floating_point = 20.5
    string = "Python is fun"
    boolean = True
    list_data = [1, 2, 3, 4, 5]
    dictionary_data = {"a": 1, "b": 2, "c": 3, "d": 4}
    
    # Conditional statement
    if integer > 5:
        message = "The number is greater than 5"
    else:
        message = "The number is not greater than 5"
    
    # Loop
    loop_data = [i for i in range(5)]
    
    # Call square function
    square_result = square(5)
    
    # Prepare data for rendering
    data = {
        "greeting": greeting,
        "integer": integer,
        "floating_point": floating_point,
        "string": string,
        "boolean": boolean,
        "list_data": list_data,
        "dictionary_data": dictionary_data,
        "message": message,
        "loop_data": loop_data,
        "square_result": square_result
    }
    
    # Render data in HTML
    return render_template_string("""
        <h1>{{ greeting }}</h1>
        <p>Integer: {{ integer }}</p>
        <p>Floating point: {{ floating_point }}</p>
        <p>String: {{ string }}</p>
        <p>Boolean: {{ boolean }}</p>
        <p>List: {{ list_data }}</p>
        <p>Dictionary: {{ dictionary_data }}</p>
        <p>Message: {{ message }}</p>
        <p>Loop data: {{ loop_data }}</p>
        <p>Square result: {{ square_result }}</p>
    """, **data)

if __name__ == "__main__":
    app.run(debug=True, host="0.0.0.0", port=5000)
```

- It would appear like this without syntax highlighting:

```
def divide_numbers(a, b):
    result = a / b
    return result

try:
    result = divide_numbers(10, 0)
    print(result)
except ZeroDivisionError as error:
    print("Error:", error)
```

Note that a good Cloud Engineer should be able to use Codeblocks for both Code and Errors that appear in the console. 

```bash
Error: division by zero
Traceback (most recent call last):
  File "example.py", line 6, in <module>
    result = divide_numbers(10, 0)
  File "example.py", line 2, in divide_numbers
    result = a / b
ZeroDivisionError: division by zero
```
> Above is an example of using Codeblock for an error that appears in bash console.

## Step 2 - Add Pictures / Images

### Adding / Uploading Files / Assets

You can add pictures to your readme file a number of different ways including:

- Using absoluting path refernecing after uploading your file.
- Relettive path by uploadng all your assets to a single location (folder) `assets/.keep`

  ### Embedding Assets

  You can embed you asset in one of the followig ways:
  
- The syntax for embedding an image is: `![]()` or
- You can use HTML markup format like so: `<img src"" />`
- The second option allows you to resize and apply custom formatting on you file after uploading

Below are examples of both methods using reletive pathing.
![Direct embed without resizing](assets/lore.jpg)

<img width="200px" src"lore.jpg" />

## Step 3 - Use Github Flavoured Task Lists

Github extends Markdown to have a list where you can check off items.[<sup>[1]</sup>](#external-references)

- [x] Finish Step 1
- [ ] Finish Step 2
- [x] Finish Step 3


## Step 4 - Use Emojis (Optional)

GitHub Flavored Markdown (GFM) supports emoji shortcodes.
Here are some examples:

| Name | Shortcode | Emoji |
| --- | --- | --- |
| Cloud | `:cloud:` | :cloud:|
| soccer | `:soccer:` | :soccer:|


## Step 5 - How to Create a Table

You can use the following markdown format to create tables:

```md
| Name | Shortcode | Emoji |
| --- | --- | --- |
| Cloud | `:cloud:` | :cloud:|
| soccer | `:soccer:` | :soccer:|
```

Github extends the functionality of markdown tables to provide more alignment and table cell formatting options. [<sup>[2]</sup>](#external-references)


## References

- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
- [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [GFM - Task Lists](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#task-lists)<sup>[1]</sup>
- [GFM - Emoji CheatSheet](https://github.com/ikatyang/emoji-cheat-sheet)<sup>[1]</sup>
- [GFM - Tables (with extension)](https://github.github.com/gfm/#tables-extension-)<sup>[2]</sup>

