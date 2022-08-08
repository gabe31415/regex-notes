Until I find a better way, this is a two part solution:

## Part I

**Temporarily replace the second QUOTE of each pair with an unused character**  
**In this case I choose "#"**

Search: `"(.+?)"`  
Replace: `"\1#`

## Part II

**Replace the spaces and replace the second temp double-quote-replacement back to a double-quote

Search: `(?-s)([^"#\r\n]*")\x20*|\x20*(#)|(\x20)+(?=.+#)`  
Replace: `(?1\1)(?2")(?3_)`  
