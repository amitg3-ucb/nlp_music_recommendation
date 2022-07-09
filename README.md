## Key Predictions
Given lyric data, audio features, and potential additional metadata, we are looking to predict the following musical characteristics for the purpose of making logical recommendations for similar songs:

- Topic
- Genre
- Song Language

Genre in particular is largely classified with audio based features, and we theorize that the introduction of lyric based features could improve model performance for out of sample genre classification. Upon detecting topic and genre alongside other provided audio and metadata features provided by Spotify + Genuis API, we believe we can use similarity/distance based modeling approaches such as KNN and KMeans to deliver logical, streamlined recommendations for similar songs.

## Key Research Questions
Preprocessing Questions
- Do specific preprocessing steps optimize future model performance more than others (ignore)

Model Dev Questions
- What model types (classical ML vs DL) generalize best out of sample for detecting different characteristics (maybe)
- Performance of Audio vs Language vs Both for DL architecures on different characteristic detection tasks (definitely)
- How does embedding size impact model performance on different tasks (maybe)
- Impact of Pre-Trained (Trainable vs not Trainable) vs Custom Embeddings on different tasks (maybe)
- How to deal with long text given variable + lengthy songs (included in different DL archictectures)
- How do we measure performance for problems where true output is density distribution? (cross entropy) What about for multi hard-class assignment (multilabel classification)? (multilabel F1)
- Problem setup for the above (binary relevance method, ...)
- Treatment for class imbalances (over/under sampling, dynamic point weighting by class proportion) (definitely)
- Impact of combining multiple models via a stacked framework for specific tasks (definitely)

Post Model Dev Questions:
- What words are most important for determining certain characteristics (identifying word importance) (definitely)
- Interesting Structure Identified (Clustering Artists/Songs/Etc) (definitely)
- Schemes for making recommendation (definitely)

## Datasets + Descriptions
[Prediction of Music Genre Dataset](Data\music_genre_audio_features_1.csv) Key contents:
- 50005 Songs
- Top Level Metadata (Song Name, Artist Name, Popularity)
- Audio Features (Captured by Spotify)
- Genre  

[Music Genre Classification Dataset](Data\music_genre_audio_features_2.csv)  Key contents:
- 17996 Songs
- Top Level Metadata (Song Name, Artist Name, Popularity)
- Audio Features (Captured by Spotify)
- Duration
- Genre  

[Music Dataset 1950-2019](Data\audio_topic_lyrics_genre.csv)  Key contents:
- 28372 Songs
- Top Level Metadata (Song Name, Artist Name, Release Data)
- Subset of Lyrics (Applied Stopword Removal and Lemmatization)
- Topic Density Breakdown + Hard Topic Assignment (Spotify LDA)
- Audio Features (Captured by Spotify)
- Genre  

[Song Lyrics from 79 Musical Genres Dataset](Data\lyrics_artist_genre)  Key contents:
- [Artist Dataset](Data\lyrics_artist_genre\artists-data.csv)

    - 4168 Artists w/ Genre Breakdown, Song Quantity at Time of Data Collection, Popularity of Artist
- [Lyrics Dataset](Data\lyrics_artist_genre\lyrics-data.csv)

    - 383570 Songs
    - Top Level Metadata (Artist Name, Song Name, Song Language)
    - Multi-language dataset (songs across multiple languages)
    - Language label
    - Song Lyrics

[Multiple Genre Playlist](Data\multi_genre_playlist)

- 7 Genres w/ a respective dataset for each
- Top Level Metadata (Artist Name, Song Name)
- Sub-Genre Breakdown
- Audio Features
- Song Duration