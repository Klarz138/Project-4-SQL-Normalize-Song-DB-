# Project-4-SQL-Normalize-Song-DB-
My largest personal project to date! In this project I worked to normalize the data from a large CSV file of the top 100 songs from the 1960s - 1970s. 

 The CSV file contained numerous headers: Year, Rank, Prefix, Wks Chart, Wks 40, Wks 10, Wks Peak, Peak Pos, Artist, Title, Time, Label-Number	, eight writers, Date Enter, Date Peak, and 75 cells of position week data. This was a lot of data to look at and understand. 

To best normalize this data, I began by looking through each of these categories for similarities. If I found similarities between the headers, I could group these into entities and form relationships. I realized there could be three main tables to best group this data: tracks, people, and position. For instance, I found the title, year, yearly rank, and date entered to best describe tracks. Each track should have data related to those columns, so I decided to group these under the track entity. I later added datePeaked into this entity, as I realized more queries could be created if this data were to be included. 

For the people table, I found there were two types of people: artists and writers. Originally, I wanted to have these be separate entities, but I realized they both contain the same attribute of a name, so it would be wasteful in resources to create a second entity when they can be grouped together. I understood additionally that we could develop two relationships between people and tracks to distinguish between artist and writer. One relationship could simply be a 1:M to describe one artist who may perform multiple tracks. But another relationship could be created to help handle the repeating group of 8 writers. A M:N relationship, with the proper linking table, could be created that shows many writers can contribute to a track, and a track can be written by more than one writer.

The final table of position was the hardest to distinguish. The data to be pulled from the top 100 would need to be the 75 cells of position week data for each track. The “for each track” section is the most critical to understand this table, as it will require data to be pulled from the track table. Therefore, I pulled the track title, year, and prefix to properly form the relationship of 1:M between track and position. 

Ultimately, I took each of these entities and developed them into an EDR, which became the basis for how I coded each table. The results of this project may be found under the appropriate file. Please let me know if you have any questions on any of the supporting documents! Thank you! 

