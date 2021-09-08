# assignment2_Pendyala
# Mahesh Pendyala
###### Guttikonda


 it's our home town.***It's a beautiful place*** and we have a special day that is my **village festival**.That is one of the best festival for our village.


------

Guttikonda Bilam, also known as Guthikonda Bilam, is a historic cave and a hill in Andhra Pradesh, India. Guttikonda or Guthikonda is the name of a nearby village, while "Bilam" is the Sanskrit word for "cave". 


# Heading for access to reach in order list and unorder list
1. Maryville
2. Kansas city
   1. Terminal depature
   2. Take a flight to seattle.
   3. Continue a flight to Doha. 
   2. Continue a flight to hyderabad.
3. Hyderabad international airport 
   1. take cab to bus station.
   2. Continue to piduguralla.
   3. Continue Piduguralla to Guttikonda.
* Places in Guttikonda.
   * Historic Caves.
   * Hills.
   * Billam.
   **[LinkAboutme.md](Aboutme.md)**

   ----
   # creating a Table foods and drinks
**Introduction:**
 The following is to create a table with atleast 4 food/drinks that you would recommend someone try. Include a short paragraph that introduces the table.

|Mandatory   |fav1            |fav2             |fav3             |fav4            |
|:--------:  |:---------:     |:---------:      |:----------:     |:----------:    |
|Food        |Mandi           |ghee idly        |puri             |Coke            |
|Location    |Guntur          |piduguralla      |Vijaywada        |Any             |
|Amount      |800             |80               |30               |100             |

-----
# Section of Quotes
>"Nothing in life is to be feared, it is only to be understood. Now is the time to understand more, so that we may fear less."
>*Author:* Marie curie. 
>“The truth is you don't know what is going to happen tomorrow. Life is a crazy ride, and nothing is guaranteed.”
>*Author:* Eminem.

----
# Heading a new section for code fencing
In geometry, the convex hull or convex envelope or convex closure of a shape is the smallest convex set that contains it. The convex hull may be defined either as the intersection of all convex sets containing a given subset of a Euclidean space, or equivalently as the set of all convex combinations of points in the subset. For a bounded subset of the plane, the convex hull may be visualized as the shape enclosed by a rubber band stretched around the subset.for link clivk here[convex hull or convex envelope](https://en.wikipedia.org/wiki/Convex_hull)


```
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }
```
[Code for Convex hull](https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html)