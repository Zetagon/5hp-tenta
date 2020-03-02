# 5hp-tenta
Org-drill f;r systemdesign

# Org-drill

Jag tror org-drill 'r installerat by default.

Documentation: https://bitbucket.org/eeeickythump/org-drill/src/default/

# Hur man syncar org-drill
Sharing, merging and synchronising item collections

Every drill item is automatically given a persistent unique "ID" the first time it is seen by Org-Drill. This means that if two different people subsequently edit or reschedule that item, Org-Drill can still tell that it is the same item. This in turn means that collections of items can be shared and edited in a collaborative manner.

There are two commands that are useful in this regard:

    org-drill-strip-all-data - this command deletes all user-specific scheduling data from every item in the current collection. (It takes the same optional 'scope' argument as org-drill to define which items will be processed by the command). User-specific data includes scheduling dates, ease factors, number of failures and repetitions, and so on. All items are reset to 'new' status. This command is useful if you want to share your item collection with someone else.
    org-drill-merge-buffers - When called from buffer A, it prompts you for another buffer (B), which must also be loaded into Emacs. This command imports all the user-specific scheduling data from buffer B into buffer A, and deletes any such information in A. Matching items are identified by their ID. Any items in B that do not exist in A are copied to A, in the same hierarchical location if all the parent headings exist, otherwise at the end of the buffer.

An example scenario:

Tim decides to learn Swedish using an item collection (.org file) made publically available by Jane. (Before publishing it Jane used 'org-drill-strip-all-data' to remove her personal scheduling data from the collection.) A few weeks later, Jane updates her collection, adding new items and revising some old ones. Tim downloads the new collection and imports his progress from his copy of the old collection, using 'org-drill-merge-buffers', using the new collection as buffer A and the old one as buffer B. He can then discard the old copy. Any items HE added to HIS copy of the old collection (buffer B) will not be lost &#x2013; they will be appended to his copy of the new collection.

Of course the sharing does not need to be 'public'. You and a friend might be learning a language or some other topic together. You each maintain a card collection. Periodically your friend sends you a copy of their collection &#x2013; you run org-drill-merge-buffers on it, always using your own collection as buffer B so that your own scheduling progress is carried over. Other times you send your friend a copy of your collection, and he or she follows the same procedure.
