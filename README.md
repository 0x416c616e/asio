# Alan's Simple IO (ASIO) module for Python 3

IO code isn't hard, but it can certainly be an unnecessarily long nuisance.

I found myself writing repetitive and lengthy code for IO stuff, such as downloading or writing files. So I made this simple IO module to make it so that you can do IO stuff in a single function call, with only 1-2 args. They all feature exception handling. So although you can technically do all this stuff even without this module, using this module makes it so much easier to do things, and in far fewer lines of code.

The functions will throw exceptions and exit the program if there is an IO issue. This is preferred behavior for my use-cases. If you would prefer not to have it like this, maybe change the sys.exit(1) lines to return -1 or something to indicate a problem without actually exiting.

## Dependencies

- Python 3
- requests module for Python 3

## Instructions

How to use it in your Python 3 script:

```
import asio
```

Example of how you can use a single function call to download and save a UTF-8 web page:

```
asio.dl_write_utf8("https://github.com/0x416c616e?tab=repositories", "first_repo_page.html")
```

How to download a file and return the HTTP response to the function invoker:

```
respose = asio.download("example.com")
```

The download() does not save to a file. It merely sends an HTTP requests, then returns the HTTP response as a variable. So the downloaded file/request is only in RAM.

How to write binary data to a file:

```
write_binary("example.jpg", image_data)
```

For a full list of functions, see the source code of asio.py.


