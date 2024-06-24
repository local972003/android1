 <TextView
                android:id="@+id/txtstud"
                android:layout_gravity="center"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Student Profile"
                android:layout_marginTop="40dp"
                android:textColor="@color/black"
                android:textSize="40dp"
                android:layout_centerHorizontal="true"/>

            <EditText
                android:id="@+id/Edtsurname"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:textSize="20dp"
                android:textColor="@color/black"
                android:layout_below="@+id/txtstud"
                android:hint="Surnamne"
                android:layout_marginTop="10dp"
                android:inputType="text"
                />
            <EditText
                android:id="@+id/Edtname"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:textSize="20dp"
                android:textColor="@color/black"
                android:layout_below="@+id/Edtsurname"
                android:hint="Name"
                android:layout_marginTop="10dp"
                android:inputType="text"
                />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="Login"
                android:textSize="30dp"
                android:layout_below="@+id/Edtname"
                android:layout_marginTop="100dp"
                android:id="@+id/btnlogin"/>

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Information"
                android:layout_gravity="center"
                android:textColor="@color/black"
                android:textSize="40dp"
                android:id="@+id/txtinf"
                android:visibility="gone"
                android:layout_below="@+id/btnlogin"
                android:layout_marginTop="30dp"
                />

           <ListView
               android:layout_width="match_parent"
               android:layout_height="wrap_content"
               android:layout_marginTop="20dp"
               android:id="@+id/listview1"/>


------------------------------------------------------------------------------



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
