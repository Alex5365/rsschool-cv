**Summary** <h6> 
1. Alexey Mazur.
2. Contact Information:
   * Telephone number: 80259527775 (recommended).
   * Viber: ccilka.
   * Mail: bitmaxmain@inbox.ru.
3. My goal is to become an experienced programmer. I would like to get a job in a reputable IT company, gain experience while working with serious projects, and also study various areas of programming. The most important thing for me in any job is to gain experience and skills. In the future, I would like to study such areas as: WEB development, learn how to design neural networks and embed them in my applications, learn how to develop mobile games using popular game engines or even written by myself.
4. Fundamentals of programming languages such as: JAWA, C ++. Knowledge of the principles of programming microcontrollers, as well as their interaction with computer software.
5. One of the fragments of my activity:
```javascript
    package com.example.criminalintent
    import android.os.Bundle;
    import android.text.Editable;
    import android.text.TextWatcher;
    import android.view.LayoutInflater;
    import android.view.View;
    import android.view.ViewGroup;
    import android.widget.Button;
    import android.widget.CheckBox;
    import android.widget.CompoundButton;
    import android.widget.EditText;
    import androidx.fragment.app.Fragment;
    import java.text.DateFormat;
    import java.util.UUID;

    public class CrimeFragment extends Fragment
    {

    private Crime mCrime;
    private EditText mTitleField;
    private Button mDateButton;
    private CheckBox mSolvedCheckBox;
    private static final String ARG_CRIME_ID = "crime_id";
    public static CrimeFragment newInstance(UUID crimeId)
    {
        Bundle args = new Bundle();
        args.putSerializable(ARG_CRIME_ID, crimeId);
        CrimeFragment fragment = new CrimeFragment();
        fragment.setArguments(args);
        return fragment;
    }

    @Override
    public void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        UUID crimeId = (UUID) getArguments().getSerializable(ARG_CRIME_ID);
        mCrime = CrimeLab.get(getActivity()).getCrime(crimeId);
    }

    @Override
    public void onStop()
    {
        super.onStop();
        //Передача обьекта Crime в CrimeListFragment
    }

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState)
    {
        View v = inflater.inflate(R.layout.fragment_crime, container, false);
        mSolvedCheckBox = v.findViewById(R.id.crime_solved);
        mSolvedCheckBox.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener()
        {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked)
            {
                mCrime.setSolved(isChecked);
            }
        });
        mDateButton = v.findViewById(R.id.crime_date);
        mDateButton.setText(mCrime.getDate().toString());
        mDateButton.setEnabled(false);
        mTitleField = v.findViewById(R.id.crime_title);
        mTitleField.setText(mCrime.getTitle());
        mTitleField.addTextChangedListener(new TextWatcher() {

            @Override
            public void beforeTextChanged(CharSequence s, int start, int count, int after) {
            }

            @Override
            public void onTextChanged(CharSequence s, int start, int before, int count) {
                mCrime.setTitle(s.toString());
            }

            @Override
            public void afterTextChanged(Editable s) {
            }
        });
        mSolvedCheckBox.setChecked(mCrime.isSolved());
        return v;
    }
}
```
6. Without experience.
7. Not.
8. Level: A0.
