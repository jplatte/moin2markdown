# moin2markdown

This script can be used to migrate MoinMoin wiki pages to Markdown (pandoc supported)

# Acknowledgements

Based on the [moni2confluence project](https://github.com/sjbotha/moin2confluence) by SJ Botha, this largely removes the confluence import step :)

# Install

    # On Debian/Ubuntu or other apt-based distro run these commands to install pandoc to convert between document formats
    sudo apt install pandoc

# Converting one page

Syntax: 

    ./moin2markdown.sh <PageName> <wiki root> <output dir>

Example: 

    ./moin2markdown.sh Certificates /data/webs/DVTech outputdir

The wiki root directory should be the one that contains the data directory

# Converting all pages in moin moin wiki

You can invoke this bash script to call the script for each page:

    for PAGE in `ls /webs/wiki/data/pages`; do echo $PAGE; ~/moin2markdown/moin2markdown.sh "$PAGE" /webs/wiki/ output/; done

# How it works
 * MoinMoin syntax is pretty close to mediawiki syntax so we convert to that first
 * We use pandoc to convert from mediawiki to markdown

# Credits

Used the code in here to see how to extract a moinmoin page source code: https://github.com/tetelle/moin

Forked and modified this confluence lua script to get from markdown to Confluence: https://github.com/jpbarrette/pandoc-confluence-writer/raw/master/confluence.lua

