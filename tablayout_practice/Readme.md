Important code parts 

I main Activity add this code 

MainActivity.java
```java

package com.example.tablayout;
import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentTransaction;
import androidx.viewpager.widget.ViewPager;

import android.os.Bundle;

import com.google.android.material.tabs.TabLayout;
public class MainActivity extends AppCompatActivity {
    ViewPager viewPager;
    TabLayout tab;
    FragmentManager fragmentManager;
    FragmentTransaction fragmentTransaction;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        viewPager=findViewById(R.id.viewPager);
        tab=findViewById(R.id.tabLayout);
        fragmentManager=getSupportFragmentManager();
        viewAdapter adapter=new viewAdapter(fragmentManager);
        viewPager.setAdapter(adapter);
        tab.setupWithViewPager(viewPager);
    }
}

```

Fragment1or2or3.java

```java

package com.example.tablayout;
import android.os.Bundle;

import androidx.fragment.app.Fragment;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
public class fragment1 extends Fragment {
    public fragment1() {
    }
    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
        // Inflate the layout for this fragment
        View view;
        view= inflater.inflate(R.layout.fragment_fragment1, container, false);
        return view;
    }
}

```

ViewAdapter.java

```java

package com.example.tablayout;
import androidx.annotation.NonNull;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentPagerAdapter;
public class viewAdapter extends FragmentPagerAdapter {
    public viewAdapter(@NonNull FragmentManager fm) {
        super(fm);
    }

    @NonNull
    @Override
    public Fragment getItem(int position) {
        if(position==0)
        {
            return new fragment1();
        }
        else if(position==1)
        {
            return new fragment2();
        }
        else
        {
            return new fragment3();
        }
    }
    @Override
    public int getCount() {
        return 3;
    }
    @Override
    public CharSequence getPageTitle(int position) {
        if(position==0)
        {
            return "Tab1";
        }
        else if(position==1)
        {
            return "Tab2";
        }
        else
        {
            return "Tab3";
        }
    }
}
```

outputs:

![Alt text](https://github.com/saiguptha2003/saiguptha2003-androidstudio_basics/blob/main/tablayout_practice/Screenshot%202023-10-09%20134645.png")
![Alt text](https://github.com/saiguptha2003/saiguptha2003-androidstudio_basics/blob/main/tablayout_practice/Screenshot%202023-10-09%20134634.png)
![Alt text](https://github.com/saiguptha2003/saiguptha2003-androidstudio_basics/blob/main/tablayout_practice/Screenshot%202023-10-09%20134623.png)




