## Project Post Mortem
Post mortems are important to understand about what happened in a project and actively think about what you learned.

Post-mortems are meant to be a blame-less space open to objective conversation about what went well and what could be improved.

Even in the examples below, where tens of millions of dollars could be lost, the best approach is to think through the series of events that led to the outcome.

Large mistakes are almost never the fault of the developer, but of the sytems and processes in place to prevent errors and problems.

[https://github.com/danluu/post-mortems](https://github.com/danluu/post-mortems)
https://blog.codinghorror.com/the-project-postmortem/



### What to Bring
Please answer the following questions. Take at least 30 minutes to prepare.

#### Approach and Process

1. What in my process and approach to this project would I do differently next time?
> I would spend more time planning and fleshing out ideas in the beginning rather than 'going with the flow' or 'adding on' stuff over time.

1. What in my process and approach to this project went well that I would repeat next time?
> Focus on incremental commits allows me to progress smoothly and spot bugs easily.
--

#### Code and Code Design

1. What in my code and program design in the project would I do differently next time?
> Using math.random() to generate everything leaves very little leeway to refactor code when the time comes.
```javascript
function generateEnemy(arr, difficulty) {
    var duplicate = 0
    var enemyObj = new Object()
    enemyObj.x = rand(difficulty, 0).toString()
    enemyObj.y = rand(7, 0).toString()
    var randText = arr[rand(arr.length, 0)]
    randText = randText.replace(/\s/g, '');
    // if (randText.includes(' '))
    //     duplicate++
    for (i in currentEnemies) {
        if (randText == currentEnemies[i].text)
            duplicate++
        if (enemyObj.x == currentEnemies[i].x && enemyObj.y == currentEnemies[i].y) {
            duplicate++
        }
    }
    if (duplicate == 0) {
        enemyObj.text = randText
        return insertEnemy(enemyObj)
        //return console.log(`Enemy Generated: ${enemyObj.text}, ${enemyObj.x}, ${enemyObj.y}`);
    } else {

    }
    // return console.log(`Duplicate found and rejected`)
}
```

1. What in my code and program design in the project went well? Is there anything I would do the same next time?
> Segmenting my functions: 
```javascript
utilities: {
    function spannify(word) {
        var spannified = []
        for (e in word) {
            var spanID = word[e]
            var spanStart = `<span id="${spanID}">`
            var spanEnd = '</span>'
            spannified.push(spanStart)
            spannified.push(word[e])
            spannified.push(spanEnd)
        }
        return spannified.join('')
    }

    //return a random integer between min(inclusive) and max value
    function rand(max, min) {
        return Math.floor(Math.random() * (max - min)) + min
    }
}
```
  For each, please include code examples.
  1. Code snippet up to 20 lines.
  2. Code design documents or architecture drawings / diagrams.

#### WDI Unit 1 Post Mortem
1. What habits did I use during this unit that helped me?
> Sleep
2. What habits did I have during this unit that I can improve on?
> Tendency to get distracted and work on 'non-critical' featurues 
3. How is the overall level of the course during this unit? (instruction, course materials, etc.)
> Sufficiently challenging - at least for the project - the exercises are mostly too simple?
