# PyMusicSearch
PyMusicSearch is a simple module for search music in youtube and music info in discogs
##### Current Version 0.1.1
#
##### Shold improve
  - More Search Options

##### New Features!
  - First Version

### Requirements
  - Python 2.7.x
  - Requests ($ pip install requests)
  - BeautifulSoup4 ($ pip install bs4)

#### PyMusicSearch can:
  - Search videos 
  - Get the top100 in youtube music 
  - Make a artist search in Discogs -Get the albuns of artist(listed in Discogs from url) 
  - Get the tracks of album(listed in Discogs from url)

##### PyMusicSearch have 6 functions that return a list of dicts:
#
###### pyms.YTSearchVideos(query)
#
    import pyms 
    query = ‘DJ Snake Turn down for what’ 
    videos = pyms.YTSearchVideos(query) 
    for video in videos: 
        print(video[‘title’], video[‘link’])
    
    '''videos[i] = {'title': videotitle, 
                  'link': videolink, 
                  'duration': videoduration, 
                  'channelname': channelname, 
                  'channelurl': channelurl, 
                  'thumbnail': thumbnailurl}'''

###### pyms.YTSearchMusicOfArtist(query)
#
    import pyms 
    query = ‘The Doors’ 
    videos = pyms.YTSearchMusicOfArtist(query) 
    if videos != [] 
        for video in videos: 
            print(video[‘title’], video[‘link’]) 
    else: print(‘Artist not found’)
    
    '''videos[i] = {'title':videotitle, 
                'link':videolink}'''
###### pyms.getYTMusicTop()
#
    import pyms
    videos = pyms.getYTMusicTop()
    for video in videos[:10]: 
        print(video[‘title’], video[‘url’])
    
    '''videos[i] = {'title': videotitle, 
                    'link': videolink, 
                    'duration': videoduration, 
                    'thumbnail': thumbnailurl}'''
###### pyms.artistSearch(query, limit=5)
#
    import pyms
    query = ‘Joy Divison’
    artists =  pyms.artistSearch(query)
    for artist in artist: 
        print(artist[‘name’])
    '''artists[i] = {'name': name, 
                     'url': url, 
                     'image': imageurl}'''
###### pyms.getAlbunsFromArtist(artisturl)
#
    import pyms
    query = ‘Sofi Tukker’
    artists =  pyms.artistSearch(query)
    artist_albuns = pyms.getAlbunsFromArtist(artisturl[0][‘url’])
    for album in artist_albuns: 
        print(album[‘name’], albuns[‘recorder’])
    '''artist_albuns[i] = {'name': name, 
                           'url': url, 
                           'artistname': artistname, 
                           'image': image, 
                           'year':year, 
                           'country': country, 
                           'recorder': recorders}'''
###### pyms.getTracksFromAlbum(albumurl):
#
    import pyms
    query = ‘Tame Impala’
    artists =  pyms.artistSearch(query)
    artist_albuns = pyms.getAlbunsFromArtist(artisturl[0][‘url’])
    album =  getTracksFromAlbum(artist_albuns[0][‘url’])
    print(album[-1][‘albumname’], ‘ - ’, album[-1][‘year’])
    for track in album[:-1]: 
        print(track[‘name’], track[‘duration’])
#
    album[i:-1] = {'name': name, 
                   'tracknum': tracknum, 
                   'duration': duration} # Tracks
    album[-1] = {'genre':albumgenre, 
                 'style':albumstyle, 
                 'albumname': albumname, 
                 'year': albumyear, 
                 'cover': coverurl} # Album info
        
## Authors

  - **Samuel Haidu** - *Initial work*

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
