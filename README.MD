# Movie Helper toolset

This toolset provides set of scripts to create and work with a local database of movies.

Scripts that suppose to be run with command:

```
python script_name.py
```

are specified as runnable.

Basic usage doesn't require any environment setup or argument passing, as all neccessary input data is requested during execution. 

Just make sure to intall all neccessary dependencies:

```
pip install -r requirements.txt
```

Specific purpose of each script in listed below.

## tmdb_helpers.py

Defines data fetching from **TMDB** API endpoints, supported by a set of utility functions. 

Core function `make_tmdb_api_request` can is used for the purpose of fetching. Expects `method`, `api_key` and an optional set of `params`. Valid call of this function will return response data as Python object.

In scope of this toolset, before any API call user's `api_key` has to be propmted manually, and the validity of the key is checked by `get_user_api_key`.

## hello_api_TMDB.py

Is runnable. Can be used to easily check the validity of your `api_key`, by making a test call to fetch some data.

## make_own_db.py

Is runnable. Creates a `MyFilmDB.json` filled with data of a thousand movies. This amount is not guaranteed however, as fetching logic is naive in implementation. Process is slow as data for each movie is fetched individually, but progress is continiously reported in console output. 

## own_db_helpers.py

Defines a single utility function `load_data` for reading a `.json` file, supposedly with movies data, from filesystem. Expects `path` to file.

## search_in_db.py

Is runnable. Attempts to load movies data from prompted `.json` file and looks up all movie titles for specified *keyword*. All matches are printed in console.

## find_similar.py

Is runnable. Can be used to generate a list of recommendations, based on a specified movie. Attempts to load movies from prompted `.json` file, finds a specific movie and looks for a best match based on collection, genres, original language and budget (weighted in mentioned order).
