# TabLayout Demo

A simple example of using TabLayout with ViewPager in Android using a unique design pattern.

# Highlights
Keep your tab title and fragment in the same class, no need to reference tab fragment and title from separate collections.

*__PagerAdapter__*

```Java
public class ViewPagerAdapter extends FragmentPagerAdapter {
    private final List<BaseTabFragment> tabs;

    ViewPagerAdapter(FragmentManager fm, List<BaseTabFragment> tabs) {
	    super(fm);
	    this.tabs = tabs;
    }

    @Override
    public Fragment getItem(int position) {
    	return tabs.get(position);
    }

    @Override
    public int getCount() {
    	return tabs.size();
    }

    @Override
    public CharSequence getPageTitle(int position) {
    	return tabs.get(position).getTabTitle();
    }
}
```

*__Setup ViewPager and TabLayout__*

```Java
viewPager.setAdapter(new ViewPagerAdapter(getSupportFragmentManager(), getTabs()));
tabLayout.setupWithViewPager(viewPager);
```

*__The getTabs()__*

```Java
private List<BaseTabFragment> getTabs() {
	return Arrays.asList(new FirstTabFragment(), new SecondTabFragment());
}
```


# Screenshot

![TabLayout Screenshot](https://github.com/owenlilly/tablayoutdemo/raw/master/photo_2016-07-21_19-45-20.jpg "TabLayout Screenshot")
