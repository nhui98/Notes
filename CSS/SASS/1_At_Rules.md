*@Mixin + @Include*
@mixin name(<Arguments...>) { }
- $arg: value  //default arg value
- $arg: null  //null arg value

- mixin can take in an entire block of styles(content block) 
- and render this block with @content

@include name()
@include name {
  //content block 
}

*@Extend*
%placeholder-name {}
@extend %placeholder-name

*@Function*
@function name(<arguments...>){
  @return
}

*@Error*
@error <expression> | errormessage
- throw an error

*@Warn*
@warn <expression>

*@Debug*
@debug <expression>
- test value during development