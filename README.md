<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Personal Spotify album recommender

Final project for the Building AI course.

## Summary

The aim of this project is to build a personal recommender for music albums on Spotify.

## Background

My motivation for this project is that I'm a big music lover and I'm slightly dissatisfied with the recommendation currently offered by Spotify.

In my perception of music as such the primary product for are not the songs by themselfs, but whole albums. I like to listen to whole albums, or some part of them if I don't have enough time to listen to the whole thing.

I've noticed that most of my favorite albums have a similar style of cover art - the picture that is on the front of the CD, vinyl record, or as the artwork for the songs on that album on an online music platform. So I'd like to get recommendations of records I haven't heard that are similar in some way, based on covers of my favourite records. Furthermore, I would of course include the music itself and its parameters in the recommendation system. The reason why I want to make recommendations based on images in the first phase is because I don't want to stay anchored in my favorite genres and gain more insight.

My goal is to get a few music albums recommended every day/week/month to play on Spotify.

## How do I expect it would be used?

1. First I need to my favourites from Spotify
   * extract the images features
2. Get a list of as many musical albums as I can get. Maybe excluding genres that I definitely don't want to recommend.
   * extract the images features also from them


## Data sources and AI methods

* You can get your favourite albums (including images) from the [Spotify API](https://developer.spotify.com/dashboard)
* Use these libraries to extract image features:
```
import cv2
from skimage.filters import prewitt_h,prewitt_v
```
* Use [Discogs Data Dump](https://discogs-data-dumps.s3.us-west-2.amazonaws.com/index.html) to get a list of music albums
* Based on the artist name and album name, try to find the album on Spotify and pair it with the list downloaded from Discogs
* Get covers for the given music albums
* Since the amout of favourites albums is not huge, I don't think it's a good idea to use a neural network. I found Cosine similarity most suitable for this type of problem

## Challenges

The challenge here is the extensive use of Spotify API, which I haven't try yet. At the same time, more computing resources will be needed to process the images and compare them with each other 

