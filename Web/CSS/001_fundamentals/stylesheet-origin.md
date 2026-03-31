# Stylesheet Origin

There are three different types of stylesheets, known as origins. These origins are the following in descending order of precedence

1. **User styles**: styles applied by the end-user
2. **Author styles**: styles applied by the website author
3. **User-agent styles**: styles applied by the browser

- By order or precedence, author styles have priority user-agent styles
- User styles are rare, and might need an extension to exist

# Additional Origins

Exceptions in precedence apply to these origins, thus will affect which declaration is applied

- [[important-declarations]] are treated as higher-priority origin
- [[css-transitions]] & [[keyframe-animations]] apply additional _virtual_ origins in the cascade so they behave predictably
- Declarations marked by the `!important` are exceptions to the style origin rule.
- [[stylesheet-origin]] styles marked `!important` have higher precedence over non-important ones, the order of precedence will be as follows
  - Important Author
  - Important User
  - Important User-Agent
  - Normal/Non-Important Author
  - Normal/Non-Important User
  - Normal/Non-Important User-Agent

[@grant2024] p. 39
