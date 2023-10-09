Important code parts 

I main Activity add this code 

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

