````java

package com.example.hello.fragment;

import com.example.hello.R;
import com.example.hello.adapter.MyListAdapter;

import android.app.Activity;
import android.content.Context;
import android.graphics.Color;
import android.os.Bundle;
import android.support.v4.app.ListFragment;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.view.ViewGroup.LayoutParams;
import android.widget.AbsListView;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.LinearLayout;
import android.widget.ListAdapter;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

public class myListFragment extends ListFragment {

		private MyListAdapter adapter = null;
		private Activity activity =null;
		View view;
		@Override
		public void onAttach(Activity activity) {
		 
			this.activity = activity;
			super.onAttach(activity);
		}
		@Override
		public void onCreate(Bundle savedInstanceState) {
			super.onCreate(savedInstanceState);
 			adapter = new MyListAdapter(getActivity());  
	        setListAdapter(adapter);  
	        
		}

		@Override
		public View onCreateView(LayoutInflater inflater, ViewGroup container,
				Bundle savedInstanceState) {
//			 View view = LayoutInflater.from(getActivity()).inflate(R.layout.fragment_list, null);
//			 TextView textview1 = (TextView) view.findViewById(R.id.textView1);
//			 textview1.setText("tag");
			  view= inflater.inflate(R.layout.fragment_list, container, false); 
			  AbsListView list = (AbsListView) view.findViewById(android.R.id.list);
			  list.setOnScrollListener(adapter);
			 return view;
//			View v = inflater.inflate(R.layout.fragment_list, container, false);
//			return v;
			
		}
		
		@Override
		public void onListItemClick(ListView l, View v, int position, long id) {
			System.out.println("Click On List Item!!!");
			super.onListItemClick(l, v, position, id);
		}

	}
 
````