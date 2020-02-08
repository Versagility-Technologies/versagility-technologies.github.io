# versagilitytechnologies.com

This repository stores the code for the Versagility Technologies website.  It leverages a Jekyll 
template from arkadianriver.github.io which is based upon the design of http://html5up.net/spectral by
the talented [@ajlkn](http://twitter.com/ajlkn).

Further documentation regarding how to leverage the theme can be found in the following locations:

- [Features](https://arkadianriver.github.io/arkadianriver.com/topics/user-guide/features.html)
- [Authoring Guide](https://arkadianriver.github.io/arkadianriver.com/topics/user-guide/)

## Using the template

1. From the repo's root directory, start Jekyll to preview as you write.
   
   ```
   bundle exec jekyll serve --future --drafts
   ```
      
1. Open a browser to http://localhost:4000 (or the port number that jekyll indicates to open).


1. Compose your first post!

   ```
   ruby compose.rb
   ```

   The [Authoring Guide](https://arkadianriver.github.io/arkadianriver.com/topics/user-guide/) describes some features 
   of the compose script that might be useful.

1. Test and publish your site:

   If you're building your site on Windows you can use the `site.bat` file;
   otherwise, just use the Jekyll commands as indicated in the site command reference below.
   
   If you use WinSCP to sync with your remote site, you can use the _publish_ option.
   To publish with WinSCP, set up a `_site.env` file as described in the comments of `site.bat`,
   being _particularly careful_ to list your site remote path and excludes correctly because the
   script uses the `syncronize -delete` option to mirror the entire remote folder to the local one.
   Otherwise, see the [various publishing options](https://jekyllrb.com/docs/deployment-methods/)
   in Jekyll's documentation.

   ```bash
   site {dev|devnof|preview|prod|publish}

     dev     Runs Jekyll in development watch mode:
               jekyll serve --future --drafts

     devnof  Runs Jekyll in development watch mode without future posts:
               jekyll serve --drafts

     preview Runs Jekyll in production watch mode:
               jekyll serve

     prod    Builds production content without watch mode:
               jekyll build

     publish Uses WinSCP's synchronize feature to mirror to a remote site.
   ```

