My Kometa (Plex Meta Manager) config
====================================

This project is focused on providing a minimalistic, refined design for displaying media collections, with an emphasis on visual clarity and an intuitive user experience. It integrates critic and audience ratings as overlays on media items, making it easy to compare public opinion and professional reviews. The rating overlays are combined to avoid clutter, creating a clean visual style while still providing valuable information at a glance.

Table of Contents
-----------------

*   [Installation](#installation)
*   [Usage](#usage)
*   [Contributing](#contributing)
*   [License](#license)
*   [Contact](#contact)

Installation
------------

There are two main ways to install Kometa:

*   Running as a Python script on your system (referred to as a "local" install)
*   Running as a Docker container

**Recommendation:** Running as a Docker container is simpler because you don’t need to worry about installing Python or its dependencies. For most users, Docker is the preferred method unless you have a specific reason to avoid it.

### Step 1: Clone the Repositories

Before proceeding with the installation, you need to clone the Kometa repository and your custom configuration repository:

1.  Clone the main Kometa repository:

    $ git clone https://github.com/Kometa-Team/Kometa.git

3.  Navigate to the Kometa folder:

    $ cd Kometa

5.  Clone your custom configuration repository into the `/config` folder:

    $ git clone https://github.com/sperea/my_kometa_plex_meta_manager_config.git config

This will ensure that the necessary configuration files are placed directly in the `/config` folder, which Kometa requires for proper setup.

### Docker Installation

Once the repositories are cloned, if you choose to install using Docker, follow these steps:

    $ docker run -it -v "$(pwd)/config:/config:rw" kometateam/kometa

This command mounts the `config` folder containing your custom configurations. Adjust the path if needed.

### Local Installation

For those who prefer a local installation, Kometa requires Python 3.8 to 3.11. Follow these steps:

1.  Install the required dependencies:

    $ pip install -r requirements.txt

If you encounter errors, try:

    $ pip install -r requirements.txt --ignore-installed

5.  Run Kometa to verify the installation:

    $ python kometa.py

### Docker Compose

If you prefer to use Docker Compose, create a `docker-compose.yml` file with the following content:

    
    services:
      kometa:
        image: kometateam/kometa
        container_name: kometa
        volumes:
          - ./config:/config
        environment:
          - TZ=Europe/Berlin
        restart: unless-stopped
        

Adjust the path to `./config` as needed. Save the file and run:

    $ docker-compose up -d

Repository Location
-------------------

To ensure proper configuration and functionality, the contents of this repository should be placed inside the `/config` folder of Kometa. This is necessary because Kometa looks for all configuration files, such as `config.yml`, collections, and overlays, within this directory.

For Docker users, mount the repository as the `/config` directory by using the following command:

    $ docker run -it -v "path/to/this/repository:/config:rw" kometateam/kometa

Make sure to replace `path/to/this/repository` with the actual path to the folder where you cloned this repository. This way, all configuration files will be properly detected by Kometa during execution.

If you are using Docker Compose, modify the volume section to match your repository path:

    
    services:
      kometa:
        image: kometateam/kometa
        container_name: kometa
        volumes:
          - /path/to/this/repository:/config
        restart: unless-stopped
        

Once you have verified that the files are correctly placed in the `/config` folder, Kometa will be able to access and apply all the settings, overlays, and collections from this repository.

# PMM Configuration

PMM offers great flexibility to customize and manage your collections and overlays. Below is a detailed guide to configure and organize your media libraries.

---

## Managing Collections and Overlays

You can remove unwanted collections or overlays by deleting the respective file path in your config file or removing them directly from each `.yml` file. While collections can be adjusted to your preference, it is recommended to avoid making changes unless you are knowledgeable, as PMM is sensitive to modifications.

---

### Meaning of Star Icons

The star icons next to the rating overlay on posters indicate ratings from popular services such as IMDb or Trakt. Below is the meaning of each color:

- **Yellow Star**: IMDb Top 250  
- **Red Star**: Trakt Top Rated  
- **Green Star**: Letterboxd Top 250  
- **Turquoise Star**: TMDb Top Rated  
- **Blue Star**: MyAnimeList Top Rated  
- **Grey Star**: AniDB Top Rated  

---

## Collection Categories

Collections are dynamically created for each library and displayed on your home screen. They serve various purposes, such as movie series, trending content, top-rated items, genres, and more.

### Anime

- Charts
- Specials
- Resolutions
- Streaming
- User-specific
- Genres and Subgenres
- Franchises
- Years and Decades
- Awards
- Studios
- Separators
- Ratings

### Audiobooks

- Genres

### Movies

- Charts
- Specials
- Resolutions
- Streaming
- User-specific
- Genres and Subgenres
- Franchises
- Years and Decades
- Awards
- Studios
- Actors
- Directors
- Authors
- Separators

### Music

- Popular Music

### Remux

- Unwatched

### Soundtracks

- Charts
- Genres
- Separators

### TV Shows

- Charts
- Specials
- Resolutions
- Streaming
- User-specific
- Genres and Subgenres
- Franchises
- Years and Decades
- Awards
- Studios
- Separators
- Ratings

### Videos

- TV Intros
- Anime Openings
- Anime Endings
- CSS Edits
- CSGO Edits
- Live Concerts

---

## Operations Categories

Operations ensure that the ratings for each item are accurate across the entire library. Preferences include IMDb for movies and TV shows and MyAnimeList for animes.

### Anime

- Mass MyAnimeList ratings update

### Movies

- Mass IMDb ratings update

### Remux

- Mass IMDb ratings update

### TV Shows

- Mass IMDb ratings update

---

## Overlay Categories

Overlays are designed to enhance the user interface by providing useful information at a glance. The emphasis is on a clean look without overloading the UI.

### Anime

- MyAnimeList Ratings
- Resolutions
- Star Symbols for MyAnimeList and AniDB
- Explicit Content

### Movies

- IMDb Ratings
- Star Symbols for IMDb, Trakt, Letterboxd, TMDb, and MyAnimeList
- Resolutions
- No Swedish Subtitles (if enabled)

### Remux

- IMDb Ratings
- Star Symbols for services
- Resolutions
- Audio Codecs

### TV Shows

- IMDb Ratings
- Star Symbols for IMDb, Trakt, and TMDb
- Resolutions
- Canceled Shows

### Videos

- TV Category
- Anime Opening Category
- Anime Ending Category
- CSS Category
- CSGO Category
- Concerts Category

---

## Collection Examples

### Audiobooks
![Audiobook Example](https://i.imgur.com/paYKsAV.png)

### Music
![Music Example](https://i.imgur.com/Cr3DSsZ.png)

---

## Overlay Examples

### Anime
![Anime Overlay Example](https://i.imgur.com/FmzDHkO.png)

### Movies
![Movies Overlay Example](https://i.imgur.com/xcq8HqX.png)

---

This document serves as a detailed guide for configuring and customizing PMM, ensuring a well-organized and visually appealing environment for your libraries.


Contributing
------------

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

To contribute, follow these steps:

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

License
-------

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

Contact
-------

Sergio Perea - [sperea.es](https://sperea.es)

Project Link: [https://github.com/sperea/my_kometa_plex_meta_manager_config](https://github.com/sperea/my_kometa_plex_meta_manager_config)