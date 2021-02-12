# Project 2: Drum Machine Server

## Basic Concept and Purpose

My plan is to make a Drum Machine Server (you can also think of it as a Drum Machine admin site) that will supply data about the drum pads and their keys/sound. 

The users will be the people creating and managing the Drum Machine site (that's you guys). It will be an exclusive site only you guys will have access to (in theory). 
You can use the site to create new drum pads and sounds, which will then be added to the Drum Machine site you made in React if you set it up right.

You don't need to have user logins on the React site. I don't think this makes sense unless you want users to be able to make and store songs, which seems too tricky.

## Technical Details You Don't Really Need To Worry About Yet

The drum pad and sound data will be stored in a similar way to the data in lines 6 to 52 of the example project. 
https://github.com/completejavascript/drum-machine/blob/master/src/components/App.js 

I can change the way the data is stored later on if you need me too.

What I'd like to do eventually is replace lines 6 to 52 in the example project, with something like this. 

    const fetchSounds = () => {
        axios.get(myServerURL).then((response) => {
          const allKeys = response.data
          const drumpadKeys = _.where(allKeys, {drumpad_id: 1})
          this.setState({ bankOne: drumpadKeys})
        });
      };
      
This request will load the drumpad keys you made and the rest of the code should be able to add them to the page if you make your app work right.
You'd have to store bankOne in this.state to make this work.
