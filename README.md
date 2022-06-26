## Key Predictions
Given lyric data, audio features, and potential additional metadata, we are looking to predict the following musical characteristics for the purpose of making logical recommendations for similar songs:

- Topic
- Genre

Genre in particular is largely classified with audio based features, and we theorize that the introduction of lyric based features could improve model performance for out of sample genre classification. Upon detecting topic and genre alongside other provided audio and metadata features provided by Spotify + Genuis API, we believe we can use similarity/distance based modeling approaches such as KNN and KMeans to deliver logical, streamlined recommendations for similar songs.

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