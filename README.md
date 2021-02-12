# Project 2: Drum Machine Server

## Basic Concept and Purpose

My plan is to make a Drum Machine Server (you can also think of it as a Drum Machine admin site) that will supply data about the drum pads and their keys/sound. 

Imagine you deploy your Drum Machine React App online and someone trys it out and says "I really like your drum machine, but you should add another key for this really cool sound". You'd have to change the code in your React App and then redeploy it, which could be a massive pain if this happens a lot. My Drum Machine Server will let you add new keys (and maybe even new drumpads) without having to change your React App at all.

I will create a separate site that stores data about the drumpads and their keys. The users for my site will be the people creating and managing the Drum Machine App (that's you guys). It will be an exclusive site only you guys have access to (in theory). You can use the site to create new drum pads and sounds, which will then be automatically added to your Drum Machine React App.

## Technical Details You Don't Really Need To Worry About Yet

The drum pad and sound data will be stored in a similar way to the bankOne data in lines 6 to 52 of the example project. 
https://github.com/completejavascript/drum-machine/blob/master/src/components/App.js 

I can change the way the data is stored later on if you need me too.

If I were adding my server to the example project, I'd replace bankOne (lines 6 to 52) with something like this. 

    const fetchKey = () => {
        axios.get(myServerURL).then((response) => {
          const allKeys = response.data
          const drumpadKeys = _.where(allKeys, {drumpad_id: 1})
          this.setState({ bankOne: drumpadKeys})
        });
      };
      
This request will load the drumpad keys you made and the rest of the code will add them to the page (if I make some slight changes, like storing bankOne as an empty array in this.state). Once you get your React App running. I'll be able to figure out how to make it connect to and use my Server.

If none of this makes sense to you, just get a React App working and I'll work my part into it afterwards.
