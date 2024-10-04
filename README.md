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

\*\*Recommendation\*\*: Running as a Docker container is simpler because you don’t need to worry about installing Python or its dependencies. For most users, Docker is the preferred method unless you have a specific reason to avoid it.

### Folder Structure

The complete configuration files for Kometa should be placed in a folder named `config`. All necessary files, such as `config.yml` and collections, should reside here.

### Docker Installation

If you choose to install using Docker, follow these steps:

    $ docker run -it -v "PATH_TO_CONFIG:/config:rw" kometateam/kometa

Replace `PATH_TO_CONFIG` with the path to your `config` folder. The `-v` flag mounts the configuration folder so that your settings are persistent.

Example command:

    $ docker run -it -v "/home/user/kometa/config:/config:rw" kometateam/kometa

### Local Installation

For those who prefer a local installation, Kometa requires Python 3.8 to 3.11. Follow these steps:

1.  Clone the repository:

    $ git clone https://github.com/Kometa-Team/Kometa

3.  Navigate to the folder:

    $ cd Kometa

5.  Install dependencies:

    $ pip install -r requirements.txt

If you encounter errors, try:

    $ pip install -r requirements.txt --ignore-installed

9.  Run Kometa to verify the installation:

    $ python kometa.py

### Docker Compose

To use Docker Compose, create a `docker-compose.yml` file with the following content:

    
    services:
      kometa:
        image: kometateam/kometa
        container_name: kometa
        volumes:
          - /path/to/config:/config
        environment:
          - TZ=Europe/Berlin
        restart: unless-stopped
        

Change the `/path/to/config` to your actual configuration path. Save and run:

    $ docker-compose up -d

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