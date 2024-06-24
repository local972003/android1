package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

import java.util.ArrayList;
import java.util.List;

public class MainActivity2 extends AppCompatActivity {
    Button Login;
    EditText edtsurname,edtname;
    TextView textView;
    ListView listView;
    ArrayList<String> list;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        edtsurname = findViewById(R.id.Edtsurname);
        edtname = findViewById(R.id.Edtname);
        Login = findViewById(R.id.btnlogin);
        listView = findViewById(R.id.listview1);
        list = new ArrayList<String>();
        textView = findViewById(R.id.txtinf);

        ArrayAdapter<String> arrayAdapter = new ArrayAdapter<String>(getApplicationContext(), android.R.layout.simple_list_item_1,list);

        Login.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String surname = edtsurname.getText().toString();
                String name = edtname.getText().toString();

                if (surname.isEmpty() || name.isEmpty())
                {
                    Toast.makeText(MainActivity2.this,"Please Enter All Details",Toast.LENGTH_LONG).show();
                }
                else
                {
                    listView.setAdapter(arrayAdapter);
                    arrayAdapter.notifyDataSetChanged();
                    textView.setVisibility(View.VISIBLE);

                    list.add("Surname : "+surname);
                    list.add("Name : "+name);

                }
            }
        });
}
}
# android1
