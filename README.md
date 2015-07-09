# image-dreamer
"Dreams" images, such as shown in the [Google Research blog post on "Inceptionism"](http://googleresearch.blogspot.ch/2015/06/inceptionism-going-deeper-into-neural.html).

## What's it do?
Using a deep neural network, it turns images like this:

![](https://cloud.githubusercontent.com/assets/235769/8487629/318827be-20c2-11e5-9b3a-ec15b0871a4d.jpg)

Into this:

![](https://cloud.githubusercontent.com/assets/235769/8487642/3f91eb74-20c2-11e5-87aa-87ed27236f22.png)

Read the [Google Research blog post on "Inceptionism"](http://googleresearch.blogspot.ch/2015/06/inceptionism-going-deeper-into-neural.html) to learn more about how it works.

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

The Vagrant file and Vagrantbox are based on those provided by [Data Science Toolbox](http://datasciencetoolbox.org/).  Big thanks to them for providing the scientific Python bootstrap I needed to get this going!

## Now what?
Have fun, hack, contribute!  This is just a starting point, I'd love to see where people take this!
