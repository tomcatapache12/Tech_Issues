// Not synchronized as token expiration (2+ hours) far exceeds job duration (15 min). 
// Rare simultaneous token generation is acceptable, with the last token saved. 
// Synchronizing this method would introduce unnecessary delays for other threads.
