# Tally string times with reduce

JS Exercises. 18th challenge of the #JavaScript30 course. 
Using JS to convert from a list of videos with mm:ss to a list which shows the total hours, minutes and seconds the videos are in total

## Technology

* [JavaScript](https://kmthorsnes.github.io/18-tally-string-times-with-reduce/) - Running solution on GitHub page

## Code
```
const timeNodes = Array.from(document.querySelectorAll('[data-time]'));

    const seconds = timeNodes
      .map(node => node.dataset.time)
      .map(timeCode => {
        const [mins, secs] = timeCode.split(':').map(parseFloat);
        return (mins * 60) + secs;
        console.log(mins, secs);
      })
      .reduce((total, vidSeconds) => total + vidSeconds);

    let secondsLeft = seconds;
    const hours = Math.floor(secondsLeft / 3600);
    secondsLeft = secondsLeft % 3600;

    const mins = Math.floor(secondsLeft / 60);
    secondsLeft = secondsLeft % 60;

    console.log(hours, mins, secondsLeft);
```
## Acknowledgments

* [#JavaScript](https://javascript30.com/) - Course and tutorial