---
 tags: ruby, strings, gsub, interpolation, kids
 languages: ruby
 level: 1
 type: lab
---

## Graduation Invitation Maker

<img src="https://s3.amazonaws.com/after-school-assets/weasley.jpg" width="150" align="left" hspace="10">
Ron Weasley is graduating from Hogwarts! He's got Percy Weasley's graduation invitations from a few years ago, which Percy wrote out by hand before sending them via owl post. Percy could have saved a lot of time by using the magic of programming to automate this task. Help Ron get these invitations printed quickly so he can spend more time playing Quidditch. 

How can you automate this task? There are the few ways we can do this...

#### gsub
The `gsub` method is a handy Ruby tool that allows you to `globally substitute` a word or letter for another word or letter within a string. That means *every time the word or letter appears in the string, it will be substituted out.* Let's take a look at how that works.

We have a fact about a bug assigned to a variable `wrong_fact`:

```ruby
wrong_fact = "Ladybugs can taste with their feet."
```
But wait, that's not a fact about ladybugs, but butterflies! Let's swap out the word "Ladybugs" for "Butterflies" using the gsub method. `gsub` takes two `parameters`. *The first one is the word you want to replace, and the second one is the word you want to replace it with*:

```ruby
right_fact = wrong_fact.gsub("Ladybugs", "Butterflies")
```

The `return value` (aka what this action produces after it's called) will be "Butterflies can taste with their feet." Then, if we type `right_fact` into our console, we'll see the fact correctly printed.

### Chaining gsubs

What if you have a sentence that you want to substitute more than one word in? We can do that by calling `gsub` more than once on the same line, through a process called `method chaining` in which you *call one method right after another*. Take a look:

```ruby
wrong_fact = "Cats fail to recover about 50 percent of the nuts they bury."
true_fact = wrong_fact.gsub("Cats", "Squirrels").gsub("50", "74")

```
### String Interpolation

There's another way to do this substitution called `string interpolation`. `String interpolation` allows us to *set a placeholder inside a string where Ruby code can be run*. We wrap whatever we want to interpolate #{inside this notation}. Oftentimes, we'll be interpolating variable names within strings.

Let's say you have this question on your biology test:

"A group of flamingos is called a #{answer}."

Then you make `answer` a variable, and assign it to the answer:

```ruby
answer = "Flamboyance"
puts "A group of flamingos is called a #{answer}"
```

Note that here we're declaring the variable `answer` before we call `puts`. We need to do it in this order because the computer reads our program sequentially. When our computer gets to `#{answer}`, it won't know what that is if `answer` isn't declared yet.

Some Rubyists write this another way:

```ruby
answer = "Flamboyance"
puts "A group of flamingos is called a " + answer
```
But personally, we think the first way looks nicer and is easier for your fellow programmers to read.

### Challenge 1 (using gsub):
Create a new Ruby file where you will code your solution. In terminal, type `touch invitation.rb`.

Copy the variable definition below, which is the original invitation that Percy used for his graduation, and paste it into `invitation.rb`. 

```ruby
percy_invitation = "The family of Percy Weasley proudly invite you to their graduation commencement on Saturday the 22nd of May 1993. Festivities will be held at The Burrow. See you then!"
```

Ron plans to have his party on May 18th, 1997 (Sunday). In `invitation.rb` use chained gsubs to customize the invitation for Ron. Remember to use puts to output your solution to the screen.

### Challenge 2 (using string interpolation):
It's 1998 and time for Ginny's graduation. Ron wants to help his little sis out. Instead of using gsub, let's use string interpolation to change the content of the invitation. Create a file for Ginny's invitation. In terminal, type `touch ginny_invitation.rb`. You'll code your solution in that file.

Copy Percy's invitation into ginny_invitation.rb again.

```ruby
invitation = "The family of Percy Weasley proudly invite you to their graduation commencement on Saturday the 22nd of May 1993. Festivities will be held at The Burrow. See you then!"
```

Now that you know what string interpolation is, assign the following content from Percy's invitation to variables in `ginny_invitation.rb`:

1. name, 'Percy'
2. the day, 'Saturday'
3. the date, '22nd'
4. the year, '1993' 

Now that we have Percy's information, it's time to change the value of these variables to reflect Ginny's info. Ginny plans to have her party on May 17th, 1998 (Sunday).

Use string interpoloation and the variables you just created to customize Percy's invitation for Ginny. As in Challenge 1, you'll want to use puts to print out your solution to the screen.
