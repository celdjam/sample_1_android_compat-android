#Add a view without a xml layout

    public Dialog onCreateDialog(Bundle savedInstanceState)
    {
        mSpinnerEspFiscal = new Spinner(getActivity());
        ViewGroup.LayoutParams params = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT,ViewGroup.LayoutParams.MATCH_PARENT);
        mSpinnerEspFiscal.setLayoutParams(params);
        int paddingVal = Convert.convertDipToPixels(getActivity(),R.dimen.dip_010);
        mSpinnerEspFiscal.setPadding(paddingVal,paddingVal,paddingVal,paddingVal);
        AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
        builder.setTitle(getString(R.string.esp_fiscal));
        builder.setView(mSpinnerEspFiscal);
        builder.setNegativeButton(getString(R.string.cancel), null);
        builder.setPositiveButton(getString(R.string.confirm),null);
        builder.setCancelable(false);
        AlertDialog dialog = builder.create();
        dialog.setOnShowListener(this);
        setupViewEspFiscal();
        return dialog;
    }
    
#Add an android listview programmatically

    public Dialog onCreateDialog(Bundle savedInstanceState)
    {
        View view = mLayoutInflater.inflate(android.R.layout.list_content, null);
        AlertDialog.Builder builder = new AlertDialog.Builder(getActivity());
        builder.setView(view);
        builder.setTitle(R.string.title_continue_regularization);
        builder.setNegativeButton(getString(R.string.cancel), null);
        builder.setCancelable(false);
        
        mListView = (ListView)view.findViewById(android.R.id.list);
        mListView.setOnItemClickListener(this);
        
        AlertDialog dialog = builder.create();
        dialog.setOnShowListener(this);
        return dialog;
     }
