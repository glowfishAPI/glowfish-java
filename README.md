
glowfi.sh in Android for the Big Web: Now with machine guns and rocket launchers.
-----------

**Installation**

    Download glowfish.aar and drop it in your app...seriously, that's it.
**Setup**

    GFGlower.glower().setCredentials('<GLOWFISH_SID>', '<GLOWFISH_AUTH_TOKEN>');

**Useage**

Get ready for some simple machine learning...

*Training*

    GFGlower.glower().train(new JSONObject("{
	    "feature_name1": [1, 2, 3, 4, ...etc],
	    "feature_name2": [9, 4, 5, 6, ...etc]
    }"), new JSONObject("{
	    "class": [4, 3, 5, 6, ...etc]
    }"), new JSONObject("{"param1": "value"}"), <GFResponse>);

*Predict*
It's important to note that predicting will throw an error if you have not trained against a data set first.

    GFGlower.glower().train(new JSONObject("{
	    "feature_name1": [1, 2, 3, 4, ...etc],
	    "feature_name2": [9, 4, 5, 6, ...etc]
    }"), new JSONObject("{
	    "class": [4, 3, 5, 6, ...etc]
    }"), new JSONObject("{"param1": "value"}"), <GFResponse>);

*Clustering*

    GFGlower.glower().train(new JSONObject("{
	    "feature_name1": [1, 2, 3, 4, ...etc],
	    "feature_name2": [9, 4, 5, 6, ...etc]
    }"), new JSONObject("{"param1": "value"}"), <GFResponse>);

*Feature Selection*

    GFGlower.glower().train(new JSONObject("{
	    "feature_name1": [1, 2, 3, 4, ...etc],
	    "feature_name2": [9, 4, 5, 6, ...etc]
    }"), new JSONObject("{
	    "class": [4, 3, 5, 6, ...etc]
    }", new JSONObject("{"param1": "value"}"), <GFResponse>);
    
*Filter Train*

    GFGlower.glower().train(new JSONArray("[1, 2, 3, 4, ...etc]"), new JSONArray("[4, 3, 5, 6, ...etc]", new JSONArray("[4, 3, 5, 6, ...etc]", new JSONObject("{"param1": "value"}"), <GFResponse>);
    
*Filter Predict*

    GFGlower.glower().train(new JSONArray("[1, 2, 3, 4, ...etc]"), new JSONArray("[4, 3, 5, 6, ...etc]", new JSONArray("[4, 3, 5, 6, ...etc]", new JSONObject("{"param1": "value"}"), <GFResponse>);
    
*Responses*

The final parameter of all calls should be a class that implements GFResponse. A GFResponse interface containts only one method:

    @Override
    public void response(GFGlower.GFApiResponse response) {
      // response is the object to use
    }
    
The GFApiResponse class is a simple map class:

    public class GFApiResponse {
        JSONObject results;
        JSONObject metrics;
        JSONObject errors;
        private JSONObject statusObj;

        Integer status;
    }

**Further Documentation**

Docs - http://glowfish.readme.io/  
Registration - http://glowfi.sh/

**Thank You**

Thanks so much to Matt Thompson (@matt) for creating Alamofire. Big props.
