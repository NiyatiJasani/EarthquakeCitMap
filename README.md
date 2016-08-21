//# EarthquakeCitMap
private void printQuakes() 
	{

int oceanQuakesCount=0;
		for(Marker earthquake: quakeMarkers){
			//If occurred in the ocean 
			if(earthquake.getProperty("country") == null){
				oceanQuakesCount++;
			//If occurred on land
			} else {
				countQuakesOnLand(earthquake.getProperty("country").toString());
			}
		}
		for(String key: hm.keySet()){
			System.out.println(key + " : "+hm.get(key));
		}
		
		System.out.println("OCEAN QUAKES: "+ oceanQuakesCount);
	}
	
	private void countQuakesOnLand(String country){
		if(!hm.containsKey(country)){
			hm.put(country, 1);
		} else {
			hm.put(country, hm.get(country)+1);
		}
	}
