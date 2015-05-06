# language-detection
Automatically exported from code.google.com/p/language-detection  
import java.util.ArrayList;    
import com.cybozu.labs.langdetect.Detector;    
import com.cybozu.labs.langdetect.DetectorFactory;    
import com.cybozu.labs.langdetect.Language;    

class LangDetectSample {    
    public void init(String profileDirectory) throws LangDetectException {    
        DetectorFactory.loadProfile(profileDirectory);    
    }    
    public String detect(String text) throws LangDetectException {    
        Detector detector = DetectorFactory.create();    
        detector.append(text);    
        return detector.detect();     
    }    
    public ArrayList<Language> detectLangs(String text) throws LangDetectException {    
        Detector detector = DetectorFactory.create();    
        detector.append(text);    
        return detector.getProbabilities();    
    }    
}   
