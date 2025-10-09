package com.example.intentloginjava;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class IntentHandler extends AppCompatActivity {

//    Intent Handling Variable
    TextView welcome;


    @SuppressLint("SetTextI18n")
    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);;
        setContentView(R.layout.activity_intent);
        welcome = findViewById(R.id.welcomeTextView);

        String username = getIntent().getStringExtra("USERNAME");
        welcome.setText("Welcome " + username + "!");
    }
}
