## [Likes Vs Dislikes](https://www.codewars.com/kata/62ad72443809a4006998218a/train/javascript)

##### Story

- YouTube had a like and a dislike button, which allowed users to express their opinions about particular content. It was set up in such a way that you cannot like and dislike a video at the same time. There are two other interesting rules to be noted about the interface: Pressing a button, which is already active, will undo your press. If you press the like button after pressing the dislike button, the like button overwrites the previous "Dislike" state. The same is true for the other way round

##### Task

- Create a function that takes in a list of button inputs and returns the final state.

#### Examples:

```python
like_or_dislike([Dislike]) => Dislike
like_or_dislike([Like,Like]) => Nothing
like_or_dislike([Dislike,Like]) => Like
like_or_dislike([Like,Dislike,Dislike]) => Nothing
```

##### Notes

- If no button is currently active, return Nothing.
- If the list is empty, return Nothing.

#### Solution:

```python
def like_or_dislike(buttons):
    current_state = "Nothing"

    for button in buttons:
        if button == current_state:
            current_state = "Nothing"
        else:
            current_state = button

    return current_state

print(like_or_dislike(["Dislike"]))  # => Dislike
print(like_or_dislike(["Like", "Like"]))  # => Nothing
print(like_or_dislike(["Dislike", "Like"]))  # => Like
print(like_or_dislike(["Like", "Dislike", "Dislike"]))  # => Nothing
```