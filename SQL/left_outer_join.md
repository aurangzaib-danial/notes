# Left Outer Join

## ON Condition VS Where (Example)

topics left joins votes.

Using 'on' votes.vote_type = like would match only liked rows of votes
but because its a left join, the rows for topics that do not have a match will also be returned.

Using 'where' votes.vote = like would filter out rows that do not have 'vote' value of 'like'.
Where ends up filtering our topics that do not have a vote.

[Great source for understanding this problem](https://searchoracle.techtarget.com/answer/LEFT-OUTER-JOIN-with-ON-condition-or-WHERE-condition)
