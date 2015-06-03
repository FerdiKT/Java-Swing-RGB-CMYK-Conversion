# RGB <-> CMYK Conversion with Java Swing 

        
        //RGB to CMYK
        double R=r/255,G = g/255,B = b/255;
        if (R<G) {
            R=G;
        }
        k = 1- Math.max(R, B);
        c = (1-R-k) / (1-k);
        m = (1-G-k) / (1-k);
        y = (1-B-k) / (1-k);
    
        //CMYK to RGB
        r = (int) (255 * (1 - c) * (1 - k));
        g = (int) (255 * (1 - m) * (1 - k));
        b = (int) (255 * (1 - y) * (1 - k));
   
