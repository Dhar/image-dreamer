# image-dreamer
"Dreams" images, such as shown in the [Google Research blog post on "Inceptionism"](http://googleresearch.blogspot.ch/2015/06/inceptionism-going-deeper-into-neural.html).

## Installation
 * Install [Vagrant](https://www.vagrantup.com/)
 * Clone this repo
 * `cd image-dreamer`
 * `vagrant up`
 * Go grab a coffee, this will take a while

## Usage
 * Copy any JPEG images you want to "dreamify" into the `image-dreamer` directory
 * `vagrant ssh`
 * `cd /vagrant`
 * `ipython dreamify.py <input JPEG filename> <output PNG filename>`
 * Freak out!

## Credits
Thanks to the great work of Google's [deepdream](https://github.com/google/deepdream/blob/master/dream.ipynb) team!

## Now what?
Have fun, hack, contribute!  This is just a starting point, I'd love to see where people take this!
