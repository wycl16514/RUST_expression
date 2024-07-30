The most useful object in near every programming language is an expression. The same apply to rust, every line you end up with semicolon it is likely an expression or a statement made up by a list of expressions.Two kinds of 
expression in rust are most useful but diffcult to understand are closure and iterators, we will dive deep into them in later sections.

Rust is an expression language. And to be noticed, an expression always have values. Eventhough rust is an upgrade version of c/c++, but a big difference is that statement(a block with several expressions) can return values:
```r
pixels[r * bounds.0 + c] = match escapes(Complex {re: point.0, im: point.1}, 255) {
    None => 0,
    Some(count) => 255 - count as 88
}
```
In aboved code match is a statement, but it can return value this is impossible in c/c++. 

In rust, block is the most general kind of expression, block is expressions wrap up by { and } . for example :
```r
let display_name = match post.author() {
    //block in { and }
    Some(author) => author.name(),
    None => {
        //block in { and }
       let network_info = post.get_network_metadata()?;
       let ip = network_info.client_address();
       //not simicolon as ending then it is the return value of the block
       ip.to_string()
    }
};
```
In aboved code, the code after Some(author)=> is block since it is wrapped in { and } and after code " None =>" is block. And notice there is not semicolon in the end of ip.to_string() which means the value of this expression
will be the returned value of the block.

Declarations are a kind of expression. The most common declaration is with keyword let. just as "let name: type = expr;" most of time type and intitalizeer are optional.
