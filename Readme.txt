else {
    // Insert a null character that is '/0' at the last of name
    // because many function like strcaecmp or strcpy read string untill
    // they find a null character
	name[strcspn(name,"\n")] = 0;
	
	//exist is the flag to check if the name is already present 
	// in the allnames or not
	exists = 0;
	
	//for all names that aready ready from the file are present in
	// allnames array
	// so in this loop we are checking if the current name (read from file)
	// is already present in the allnames or not
	for(i=0; i<max ;i++) {
	    // condition if name already present or not
		if(strcasecmp(allnames[i], name) == 0) {
		    //if name already presetn then update flag exists as 1 
		    // so that we can use this flag to update the count
			exists = 1;
			
			//now break from the loop so that we can remember the 
			// value of i to update the count array
			break;
		}
	}
	
	//check if name does not already exists 
	if(!exists) {
	    
	    // copy the new name to the allnames array
		strcpy(allnames[max],name);
		
		//update the count for the current name
		count[max]++;
		
		//max represents the total names present in the allnames array 
		// it means it is the size of allnames array
		max++;
	}
	else
	//now if name already present in the allnames array 
	// then increae the count for the same name 
		count[i]++;
}
