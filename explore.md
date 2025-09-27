After cloning I did the following:

“How big is the dataset?” 
This is what I got after running `wc -l clean_dialog.csv`
“36860 clean_dialog.csv”
So it should be 36859 lines of dialog and 1 header line.
“What’s the structure of the data? (i.e., what are the field and what are values in them)“
This is what I got after running  `head -n 3 clean_dialog.csv`

"title","writer","pony","dialog"
"Friendship is Magic, part 1","Lauren Faust","Narrator","Once upon a time, in the magical land of Equestria, there were two regal sisters who ruled together and created harmony for all the land. To do this, the eldest used her unicorn powers to raise the sun at dawn; the younger brought out the moon to begin the night. Thus, the two sisters maintained balance for their kingdom and their subjects, all the different types of ponies. But as time went on, the younger sister became resentful. The ponies relished and played in the day her elder sister brought forth, but shunned and slept through her beautiful night. One fateful day, the younger unicorn refused to lower the moon to make way for the dawn. The elder sister tried to reason with her, but the bitterness in the young one's heart had transformed her into a wicked mare of darkness: Nightmare Moon."
"Friendship is Magic, part 1","Lauren Faust","Narrator","She vowed that she would shroud the land in eternal night. Reluctantly, the elder sister harnessed the most powerful magic known to ponydom: the Elements of Harmony. Using the magic of the Elements of Harmony, she defeated her younger sister, and banished her permanently in the moon. The elder sister took on responsibility for both..."

 So there is a title, a writer, a pony, and a dialog field. All of the values are strings, title is the title of the episode, writer is who wrote the script, pony is the character speaking (sometimes it’s a “Narrator” or some other non-pony character) and lastly dialog is just what the character says

“How many episodes does it cover?”
This is what I got after running `cut -d',' -f1 clean* | uniq | wc -l`

197. But this counted the title row so subtracting one, this dataset covers 196 episodes.

“During the exploration phase, find at least one aspect of the dataset that is unexpected – meaning that it seems like it could create issues for later analysis.“

Some of the character names are at times blended in with others: “_some_pony’s_name and Narrator or some other pony” making it harder to count the actual times the pony spoke 

