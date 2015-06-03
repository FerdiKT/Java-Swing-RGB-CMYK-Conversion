# RGB <-> CMYK Conversion with Java Swing 

<code>
public void CMYKConversion() {
        rColor.setText(String.valueOf(jSlider1.getValue()));
        r = jSlider1.getValue();
        gColor.setText(String.valueOf(jSlider2.getValue()));
        g = jSlider2.getValue();
        bColor.setText(String.valueOf(jSlider3.getValue()));
        b = jSlider3.getValue();
        
        //Set to CMYK
        double R=r/255,G = g/255,B = b/255;
        if (R<G) {
            R=G;
        }
        k = 1- Math.max(R, B);
        c = (1-R-k) / (1-k);
        m = (1-G-k) / (1-k);
        y = (1-B-k) / (1-k);
        
        jSlider4.setValue((int) (c * 1000));
        cColor.setText(String.valueOf(c));
        jSlider5.setValue((int) (m * 1000));
        mColor.setText(String.valueOf(m));
        jSlider6.setValue((int) (y * 1000));
        yColor.setText(String.valueOf(y));
        jSlider7.setValue((int) (k * 1000));
        kColor.setText(String.valueOf(k));
        
        this.getContentPane().setBackground(new Color((int)r, (int)g, (int)b));
        author.setForeground(new Color(255-(int)r, 255-(int)g, 255-(int)b));
    }

    public void RGBConversion() {
        c = (double)jSlider4.getValue() / 1000;
        cColor.setText(String.valueOf(c));
        m = (double)jSlider5.getValue() / 1000;
        mColor.setText(String.valueOf(m));
        y = (double)jSlider6.getValue() / 1000;
        yColor.setText(String.valueOf(y));
        k = (double)jSlider7.getValue() / 1000;
        kColor.setText(String.valueOf(k));
        
        r = (int) (255 * (1 - c) * (1 - k));
        g = (int) (255 * (1 - m) * (1 - k));
        b = (int) (255 * (1 - y) * (1 - k));
        
        rColor.setText(String.valueOf(r));
        jSlider1.setValue((int)r);
        gColor.setText(String.valueOf(g));
        jSlider2.setValue((int)g);
        bColor.setText(String.valueOf(b));
        jSlider3.setValue((int)b);
        
        this.getContentPane().setBackground(new Color((int)r, (int)g, (int)b));
        author.setForeground(new Color(255-(int)r, 255-(int)g, 255-(int)b));
    }
</code>
