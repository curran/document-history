# document-history
A space efficient representation for text document revisions.

When developing a persistent representation for editable documents (such as blog posts), the question arises "What about storing the edit history?" There are two primary strategies for doing this, you can either

 * store the full text of each revision, or
 * store the differences between revisions.

Storing the full text of each revision is simple to implement, but not space efficient. Imagine a text document that is 1000 lines long. If a user edits a single line of that document 100 times, it causes 1000 * 100 = 100000 lines of text to be stored for the revision history with this approach. Even though this is not space efficient, this strategy is commonly used. For example, [Wikipedia stores the full text of each revision](https://www.mediawiki.org/wiki/Manual:Text_table).

Storing the differences between revisions is a more space efficient approach, but is more complex to implement. Imagine a text document that is 1000 lines long. If a user edits a single line of that document 100 times, it causes (roughly) 1000 + (1 * 100) = 1100 lines of text to be stored for the revision history with this approach. ** The purpose of this library is to make it easy to implement this diff-based approach for storing document revisions. **
