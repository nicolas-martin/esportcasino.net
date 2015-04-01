### Bet 
|Id       | RoundId 	|itemsJson  |itemsvalue  |SteamId|TradeId |
|---------|---------	|----	  |----   |------ |---- |
|   1     |    1     	|	{}    |  5    |2222   |667135|
|   2     |    1     	|	 {}   |  6    |3333   |55167|
|   3     |     1 	  |	 {}   |  2    |4444   |    54617 |


###Round
| Id     | skimItemsJson    |TradeId    |TimeStarted  | TimeEnded 	|winnerSteamId 	|Value  | IsRoundRunning |
|---------|-------- |-----------|-------------|-------------|------   |---    |-----|
|1        | {}        | 79857   | ...         |....         |33333    |44$    |TRUE|


```SQL
CREATE TABLE Round (
    roundId int    NOT NULL ,
    skimItemsJson text    NOT NULL ,
    timestarted timestamp    NOT NULL ,
    timefinished timestamp    NOT NULL ,
    winnerSteamId int    NOT NULL ,
    IsRoundRunning bool    NOT NULL ,
    CONSTRAINT Round_pk PRIMARY KEY (roundId)
);
```

```SQL
-- Table bets
CREATE TABLE bets (
    betId int    NOT NULL ,
    itemsJson char(12)    NOT NULL ,
    SteamId int    NOT NULL ,
    itemsvalue numeric(15,2)    NOT NULL ,
    roundId int    NOT NULL ,
    CONSTRAINT bets_pk PRIMARY KEY (betId)
);
```
