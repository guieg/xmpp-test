# XMPP Test


# Setup

1. it's needed to build all user images:

    ```
    docker compose build
    ```

2. Then, start prosody:

    ```
    docker compose up -d prosody
    ```

3. Adding users:

    ```
    $ docker exec -u root -it prosody bash
    $ prosodyctl adduser nurture@prosody
    $ prosodyctl adduser threefold@prosody
    $ prosodyctl adduser kinship@prosody
    ```

# Run

1. Start the profanity clients for each user:

    ```
    docker compose run -it admin
    docker compose run -it nurture
    docker compose run -it threefold
    docker compose run -it kinship
    ```

2. On each profanity session login using:

    ```
    /connect admin@prosody tls disable
    /connect nurture@prosody tls disable
    /connect threefold@prosody tls disable
    /connect kinship@prosody tls disable
    ```