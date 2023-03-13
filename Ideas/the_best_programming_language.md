# The Best Programming Language

What do you think is the best programming language?

Did you decide?

Good, your choice is 100% subjective and objective right and everyone agrees with you. \
Your language is the best, but you should not write everything in it.

## Choosing the right tool

You are stranded on a small island; the fastest car won't save you. \
In the middle of the desert a raft is useless. \
A camel will never win a drag race.

In short: Look at the task and choose the right language

- Microcontroller: C
- Game Development: C#
- Scripts and Machine Learning: Python
- ...

These are just examples. Every task has several suitable languages and every language has several applications. Every big language is general-purpose, but the language design and community shape the language to their needs.

It is not possible to write everything from scratch, you will use some packets. The right package for your task outweighs the advantages from the best language without a fitting packet.

## Perfection might be better, but not worth the effort

Maybe the tool is already chosen; somebody started a project in another language as the subjective and objective best one.

If you want (or must) expand the project you have 2 possibilities.

1. Rewrite the project in the better language
2. Write your extension in the worse language

You want to rewrite the project and then add the nice extension. This will be a lot of work, are you sure this is worth it?

- All the common language might look similar, but a translation has always it's quirks
- Your version with extension is split from the original

A rewrite is only worth it, if the positives outweighs the negatives.

- Positives
	- Your version of the project is in the better language with all the nice features
	- You can write the extension and future extensions in the better language
- Negatives
	- A lot of work to translate
	- 2 versions of the project exist
	- Your extension can't be merged with the original

For any project with a reasonable large size a rewrite won't be worth it.

## Notes

### Speed

But my language is 5 times faster than the other one in this benchmark. \
Benchmarks are an estimate of the "speed" of the language, not the speed of your application.

- The network request which takes 99% of the execution time won't be faster
- 0.5 milliseconds and 0.1 milliseconds don't feel different.

### Garbing Collection

Garbage collection might cause lag spikes at random times for random durations, but is this a problem? Languages use garbage collection for other reasons as causing lag spikes, so manage the memory yourself or life with the borrow checker.

## Language Task Matrix

Note: Based on my limited knowledge and prejudice

|   Task \ Language |  C  | Rust | C++ | Go  | C#  | Java | Java-/TypeScript | Python |
| ----------------: | :-: | :--: | :-: | :-: | :-: | :--: | :--------------: | :----: |
|   Microcontroller |  X  |  X   |  X  | (X) |     |      |                  |        |
|    Game Framework |  X  |  X   |  X  |     |     |      |                  |        |
|  Game Development |     |  X   |  X  |  X  |  X  |  X   |       (X)        |  (X)   |
|   GUI Application |     |  X   |  X  |  X  |  X  |  X   |        X         |   X    |
|           Website |     | (X)  |     |     | (X) |      |        X         |        |
| Automation-Script |     |      |     |     | (X) |      |        X         |   X    |

Legend:
- X: recommendation
- (X): limited recommendation

## Closing remarks

Any corrections and extensions are welcome.

Just kidding, write everything in Rust!
