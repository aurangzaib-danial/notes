# Common usage

## Meta-characters
Meta characters describe a group of characters, like `\d` describes a digit.

## Numbers
```ruby
\d #=> for digits
\D #=> for non digits
```

## Wildcard - The dot
Dot can represent anything. It's our joker in regex.
**simple dot overwrites the regular dot, use escaping for writing dot for a sentence**

## Range of Characters [abc123]
Each character inside brackets will be tried to match a spot in the string.

```ruby
'cats'.match?(/cat[abcs]/) #=> true
'cats'.match?(/cat[a-zA-Z]/) #=> true
```

## boundry character
This matches the boundary between a word and a non-word character. It's most useful in capturing entire words (for example by using the pattern \w+\b)

## Whitespace characters 
\s space \t tab \n newline \r return and \S for non whitespace

## Repitition
All the characters are matched for a single character and we want to match repeated characters, instead of reapeating the character we can specify how many times character will repeat.

```ruby
a{2}
[1-9]{5}
```

## Alphnumeric Characters
Alphanumeric character [a-zA-Z0-9_] just us \w and \W for non-alpha

## Aribitrary number of repitition *, +
- Keelne Star or * 0 or more of a certain character (lazy)
- Keelne Plus or + 1 or more of a certain character (strict)
- These can be used with meta or normal characters

## Optional Character
This character allows zero or one of the precreding character to be matched

```ruby
'abc'.match? /ab?c/ #=> will match ac and abc 
```

## Start and end
Sometimes we do not want to match in the middle of the line but at the start or at the end or both.

**^** for the start of the link and **$** for the end of the line

## Groups
Sometimes we match certain a complete text but we only part a specific info out of it. Then we use groups.
What if I want to find all the images with png format and only use the name of file.
Its important that I match png part of it but I only need name, if I try to match just by name, I would get other files with other formats as well.

```ruby
'IMG1.png'.match? /^(IMG\d+)\.png$/
# We only want extract specific info after matching.

# We can also use Nested capture groups, we might want to extract a group out of group
# ^(IMG(\d+))\.png$

# Skipping a group ( /(?:skip)(keep)/
```

## Conditionals
Conditionals, we do not want to use quantifiers everywhere because we do not what we will get. We can be exact as well instead of being fancy.

```
/milk|bread|juice/
```
