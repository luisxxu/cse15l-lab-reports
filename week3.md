code

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                returnString += parameters[1] + "\n";
            }
            return String.format(returnString);
        }
        return "404 Not Found!";
    }
    
