# RGB <-> CMYK Conversion with Java Swing 

        
##RGB to CMYK
        // r,g,b variables get their values from Sliders.
        // 
        double R=r/255,G = g/255,B = b/255;
        if (R<G) {
            R=G;
        }
        k = 1- Math.max(R, B);
        c = (1-R-k) / (1-k);
        m = (1-G-k) / (1-k);
        y = (1-B-k) / (1-k);
    
##CMYK to RGB
        // c,m,y,k variables get values from Sliders.
        // in the project file I divide this variables 1000 for sliders. 
        // Because sliders need integer value, CMYK should between 0 and 1.
        r = (int) (255 * (1 - c) * (1 - k));
        g = (int) (255 * (1 - m) * (1 - k));
        b = (int) (255 * (1 - y) * (1 - k));
   
<img src="https://lh3.googleusercontent.com/ZmaisQTyKToQCGHtq-MiFpg0_a49anEIrKTl2SYC2kh4=w1280-h721-no"/>
